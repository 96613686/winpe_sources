# ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData(IUnknown *)

- ea: `0x180003f60`
- end: `0x180004135`
- name: `?FindOrAddAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@@Z`
- size: `469`
- prototype: `struct ADM_SECURE_DATA *__fastcall(struct IUnknown *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800025f0`
- `0x180002850`
- `0x180002c40`
- `0x180002e90`

## callees

- `0x180001124`
- `0x18000313c`
- `0x18000333c`
- `0x18000340c`
- `0x180003d54`
- `0x180003dd8`
- `0x180003f60`
- `0x180007234`
- `0x180008410`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003f90`
- `KERNEL32!EnterCriticalSection` at `0x180003fdf`
- `KERNEL32!EnterCriticalSection` at `0x180003f90`
- `KERNEL32!EnterCriticalSection` at `0x180003fdf`
- `KERNEL32!LeaveCriticalSection` at `0x180003fb3`
- `KERNEL32!LeaveCriticalSection` at `0x18000410d`
- `KERNEL32!LeaveCriticalSection` at `0x180003fb3`
- `KERNEL32!LeaveCriticalSection` at `0x18000410d`
- `RPCRT4!NdrClientCall2` at `0x180003fcf`
- `RPCRT4!NdrClientCall2` at `0x180003fcf`

## pseudocode

```c
struct ADM_SECURE_DATA *__fastcall ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData(struct IUnknown *a1)
{
  struct ADM_GUID_MAP *v2; // rbx
  struct ADM_SECURE_DATA *v3; // rdi
  int Pointer; // ebx
  char *v5; // rax
  int v6; // r8d
  struct ADM_GUID_MAP *v7; // rax
  struct ADM_SECURE_DATA *v8; // rax
  char v10; // [rsp+28h] [rbp-50h]
  struct _GUID v11; // [rsp+40h] [rbp-38h] BYREF
  struct _GUID v12; // [rsp+50h] [rbp-28h] BYREF

  v12 = 0;
  EnterCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  v2 = ADM_GUID_MAP::FindAndReferenceGuidMap(a1);
  if ( v2 )
  {
LABEL_11:
    v3 = ADM_SECURE_DATA::FindAndReferenceClientSecureData(v2);
    if ( !v3 )
    {
      v11 = *(struct _GUID *)((char *)v2 + 76);
      v8 = ADM_SECURE_DATA::CreateADM_SECURE_DATA(a1, &v11, 0);
      v3 = v8;
      if ( v8 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v8 + 6);
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\proxy\\secdat.cxx",
          648,
          "ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData",
          "ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData: out of memory\n",
          v10);
      }
    }
    if ( v2 && _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 6, 0xFFFFFFFF) == 1 )
    {
      ADM_GUID_MAP::~ADM_GUID_MAP(v2);
      operator delete(v2);
    }
    goto LABEL_19;
  }
  v3 = 0;
  LeaveCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  Pointer = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_18000B8A6, a1, &v12).Pointer;
  EnterCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  if ( Pointer >= 0 )
  {
    v2 = ADM_GUID_MAP::FindAndReferenceGuidMap(a1);
    if ( !v2 )
    {
      v11 = v12;
      v7 = ADM_GUID_MAP::CreateADM_GUID_MAP(a1, &v11);
      v2 = v7;
      if ( !v7 )
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_19;
        v5 = "ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData: out of memory\n";
        v6 = 625;
        goto LABEL_5;
      }
      _InterlockedIncrement((volatile signed __int32 *)v7 + 6);
    }
    goto LABEL_11;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v5 = "ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData: IMSAdminBaseW_R_GetServerGuid_Proxy failed\n";
    v6 = 611;
LABEL_5:
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "inetsrv\\iis\\mb\\proxy\\secdat.cxx",
      v6,
      "ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData",
      v5,
      v10);
  }
LABEL_19:
  LeaveCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  return v3;
}

```

## disassembly

```asm
0x180003f60  mov     [rsp+arg_8], rbx
0x180003f65  mov     [rsp+arg_10], rsi
0x180003f6a  push    rdi
0x180003f6b  sub     rsp, 70h
0x180003f6f  mov     rax, cs:__security_cookie
0x180003f76  xor     rax, rsp
0x180003f79  mov     [rsp+78h+var_18], rax
0x180003f7e  mov     rsi, rcx
0x180003f81  xorps   xmm0, xmm0
0x180003f84  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003f8b  movups  [rsp+78h+var_28], xmm0
0x180003f90  call    cs:__imp_EnterCriticalSection
0x180003f96  mov     rcx, rsi; struct IUnknown *
0x180003f99  call    ?FindAndReferenceGuidMap@ADM_GUID_MAP@@SAPEAV1@PEAUIUnknown@@@Z; ADM_GUID_MAP::FindAndReferenceGuidMap(IUnknown *)
0x180003f9e  mov     rbx, rax
0x180003fa1  test    rax, rax
0x180003fa4  jnz     loc_180004077
0x180003faa  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003fb1  xor     edi, edi
0x180003fb3  call    cs:__imp_LeaveCriticalSection
0x180003fb9  lea     r9, [rsp+78h+var_28]
0x180003fbe  mov     r8, rsi
0x180003fc1  lea     rdx, byte_18000B8A6; pFormat
0x180003fc8  lea     rcx, pStubDescriptor; pStubDescriptor
0x180003fcf  call    cs:__imp_NdrClientCall2
0x180003fd5  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003fdc  mov     rbx, rax
0x180003fdf  call    cs:__imp_EnterCriticalSection
0x180003fe5  test    ebx, ebx
0x180003fe7  jns     short loc_180004027
0x180003fe9  test    byte ptr cs:g_dwDebugFlags, 3
0x180003ff0  jz      loc_180004106
0x180003ff6  lea     rax, aAdmSecureDataF_2; "ADM_SECURE_DATA::FindOrAddAndReferenceC"...
0x180003ffd  mov     r8d, 263h; unsigned int
0x180004003  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000400a  lea     r9, aAdmSecureDataF; "ADM_SECURE_DATA::FindOrAddAndReferenceC"...
0x180004011  lea     rdx, aInetsrvIisMbPr; "inetsrv\\iis\\mb\\proxy\\secdat.cxx"
0x180004018  mov     [rsp+78h+var_58], rax; char *
0x18000401d  call    PuDbgPrint
0x180004022  jmp     loc_180004106
0x180004027  mov     rcx, rsi; struct IUnknown *
0x18000402a  call    ?FindAndReferenceGuidMap@ADM_GUID_MAP@@SAPEAV1@PEAUIUnknown@@@Z; ADM_GUID_MAP::FindAndReferenceGuidMap(IUnknown *)
0x18000402f  mov     rbx, rax
0x180004032  test    rax, rax
0x180004035  jnz     short loc_180004077
0x180004037  movaps  xmm0, [rsp+78h+var_28]
0x18000403c  lea     rdx, [rsp+78h+var_38]; struct _GUID
0x180004041  mov     rcx, rsi; struct IUnknown *
0x180004044  movdqa  xmmword ptr [rsp+78h+var_38.Data1], xmm0
0x18000404a  call    ?CreateADM_GUID_MAP@ADM_GUID_MAP@@SAPEAV1@PEAUIUnknown@@U_GUID@@@Z; ADM_GUID_MAP::CreateADM_GUID_MAP(IUnknown *,_GUID)
0x18000404f  mov     rbx, rax
0x180004052  test    rax, rax
0x180004055  jnz     short loc_180004073
0x180004057  test    byte ptr cs:g_dwDebugFlags, 3
0x18000405e  jz      loc_180004106
0x180004064  lea     rax, aAdmSecureDataF_1; "ADM_SECURE_DATA::FindOrAddAndReferenceC"...
0x18000406b  mov     r8d, 271h
0x180004071  jmp     short loc_180004003
0x180004073  lock inc dword ptr [rax+18h]
0x180004077  mov     rcx, rbx; struct ADM_GUID_MAP *
0x18000407a  call    ?FindAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAVADM_GUID_MAP@@@Z; ADM_SECURE_DATA::FindAndReferenceClientSecureData(ADM_GUID_MAP *)
0x18000407f  mov     rdi, rax
0x180004082  test    rax, rax
0x180004085  jnz     short loc_1800040E4
0x180004087  movups  xmm0, xmmword ptr [rbx+4Ch]
0x18000408b  xor     r8d, r8d; int
0x18000408e  lea     rdx, [rsp+78h+var_38]; struct _GUID
0x180004093  mov     rcx, rsi; struct IUnknown *
0x180004096  movdqu  xmmword ptr [rsp+78h+var_38.Data1], xmm0
0x18000409c  call    ?CreateADM_SECURE_DATA@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@U_GUID@@H@Z; ADM_SECURE_DATA::CreateADM_SECURE_DATA(IUnknown *,_GUID,int)
0x1800040a1  mov     rdi, rax
0x1800040a4  test    rax, rax
0x1800040a7  jnz     short loc_1800040E0
0x1800040a9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800040b0  jz      short loc_1800040E4
0x1800040b2  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800040b9  lea     rax, aAdmSecureDataF_1; "ADM_SECURE_DATA::FindOrAddAndReferenceC"...
0x1800040c0  lea     r9, aAdmSecureDataF; "ADM_SECURE_DATA::FindOrAddAndReferenceC"...
0x1800040c7  mov     [rsp+78h+var_58], rax; char *
0x1800040cc  mov     r8d, 288h; unsigned int
0x1800040d2  lea     rdx, aInetsrvIisMbPr; "inetsrv\\iis\\mb\\proxy\\secdat.cxx"
0x1800040d9  call    PuDbgPrint
0x1800040de  jmp     short loc_1800040E4
0x1800040e0  lock inc dword ptr [rax+18h]
0x1800040e4  test    rbx, rbx
0x1800040e7  jz      short loc_180004106
0x1800040e9  or      eax, 0FFFFFFFFh
0x1800040ec  lock xadd [rbx+18h], eax
0x1800040f1  cmp     eax, 1
0x1800040f4  jnz     short loc_180004106
0x1800040f6  mov     rcx, rbx; this
0x1800040f9  call    ??1ADM_GUID_MAP@@QEAA@XZ; ADM_GUID_MAP::~ADM_GUID_MAP(void)
0x1800040fe  mov     rcx, rbx; Block
0x180004101  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004106  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000410d  call    cs:__imp_LeaveCriticalSection
0x180004113  mov     rax, rdi
0x180004116  mov     rcx, [rsp+78h+var_18]
0x18000411b  xor     rcx, rsp; StackCookie
0x18000411e  call    __security_check_cookie
0x180004123  lea     r11, [rsp+78h+var_8]
0x180004128  mov     rbx, [r11+18h]
0x18000412c  mov     rsi, [r11+20h]
0x180004130  mov     rsp, r11
0x180004133  pop     rdi
0x180004134  retn
```
