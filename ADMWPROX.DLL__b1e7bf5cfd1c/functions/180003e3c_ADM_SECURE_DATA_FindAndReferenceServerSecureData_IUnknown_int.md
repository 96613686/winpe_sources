# ADM_SECURE_DATA::FindAndReferenceServerSecureData(IUnknown *,int)

- ea: `0x180003e3c`
- end: `0x180003f57`
- name: `?FindAndReferenceServerSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@H@Z`
- size: `283`
- prototype: `struct ADM_SECURE_DATA *__fastcall(struct IUnknown *, int)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ce0`
- `0x180001f30`
- `0x1800020f0`
- `0x180002170`
- `0x180002240`
- `0x1800022e0`
- `0x180002a3c`
- `0x180003090`

## callees

- `0x18000340c`
- `0x180003e3c`
- `0x180007234`
- `0x180008410`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003e66`
- `KERNEL32!EnterCriticalSection` at `0x180003e66`
- `KERNEL32!LeaveCriticalSection` at `0x180003f2f`
- `KERNEL32!LeaveCriticalSection` at `0x180003f2f`
- `ole32!CoCreateGuid` at `0x180003ea1`
- `ole32!CoCreateGuid` at `0x180003ea1`

## string_xrefs

- `0x180003efc`: `ADM_SECURE_DATA::FindAndReferenceServerSecureData: CoCreateGuid failed\n`

## pseudocode

```c
struct ADM_SECURE_DATA *__fastcall ADM_SECURE_DATA::FindAndReferenceServerSecureData(struct IUnknown *a1, int a2)
{
  ADM_SECURE_DATA *i; // rbx
  struct ADM_SECURE_DATA *v5; // rax
  char *v6; // rax
  unsigned int v7; // r8d
  char v9; // [rsp+28h] [rbp-40h]
  struct _GUID v10; // [rsp+30h] [rbp-38h] BYREF
  GUID pguid; // [rsp+40h] [rbp-28h] BYREF

  EnterCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
  for ( i = ADM_SECURE_DATA::sm_ServerSecureDataListHead;
        i != (ADM_SECURE_DATA *)&ADM_SECURE_DATA::sm_ServerSecureDataListHead;
        i = *(ADM_SECURE_DATA **)i )
  {
    if ( *((struct IUnknown **)i + 2) == a1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)i + 6);
      goto LABEL_15;
    }
  }
  i = 0;
  if ( !a2 )
    goto LABEL_15;
  pguid = 0;
  if ( CoCreateGuid(&pguid) < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v6 = "ADM_SECURE_DATA::FindAndReferenceServerSecureData: CoCreateGuid failed\n";
      v7 = 558;
LABEL_14:
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\proxy\\secdat.cxx",
        v7,
        "ADM_SECURE_DATA::FindAndReferenceServerSecureData",
        v6,
        v9);
    }
  }
  else
  {
    v10 = pguid;
    v5 = ADM_SECURE_DATA::CreateADM_SECURE_DATA(a1, &v10, 1);
    i = v5;
    if ( !v5 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_15;
      v6 = "ADM_SECURE_DATA::FindAndReferenceServerSecureData: out of memory\n";
      v7 = 546;
      goto LABEL_14;
    }
    _InterlockedIncrement((volatile signed __int32 *)v5 + 6);
  }
LABEL_15:
  LeaveCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
  return i;
}

```

## disassembly

```asm
0x180003e3c  mov     [rsp+arg_8], rbx
0x180003e41  mov     [rsp+arg_10], rsi
0x180003e46  push    rdi
0x180003e47  sub     rsp, 60h
0x180003e4b  mov     rax, cs:__security_cookie
0x180003e52  xor     rax, rsp
0x180003e55  mov     [rsp+68h+var_18], rax
0x180003e5a  mov     rdi, rcx
0x180003e5d  mov     esi, edx
0x180003e5f  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003e66  call    cs:__imp_EnterCriticalSection
0x180003e6c  mov     rbx, cs:?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x180003e73  lea     rax, ?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x180003e7a  jmp     short loc_180003E85
0x180003e7c  cmp     [rbx+10h], rdi
0x180003e80  jz      short loc_180003EE7
0x180003e82  mov     rbx, [rbx]
0x180003e85  cmp     rbx, rax
0x180003e88  jnz     short loc_180003E7C
0x180003e8a  xor     ebx, ebx
0x180003e8c  test    esi, esi
0x180003e8e  jz      loc_180003F28
0x180003e94  xorps   xmm0, xmm0
0x180003e97  lea     rcx, [rsp+68h+pguid]; pguid
0x180003e9c  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x180003ea1  call    cs:__imp_CoCreateGuid
0x180003ea7  test    eax, eax
0x180003ea9  js      short loc_180003EF3
0x180003eab  movaps  xmm0, xmmword ptr [rsp+68h+pguid.Data1]
0x180003eb0  lea     r8d, [rbx+1]; int
0x180003eb4  lea     rdx, [rsp+68h+var_38]; struct _GUID
0x180003eb9  movdqa  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x180003ebf  mov     rcx, rdi; struct IUnknown *
0x180003ec2  call    ?CreateADM_SECURE_DATA@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@U_GUID@@H@Z; ADM_SECURE_DATA::CreateADM_SECURE_DATA(IUnknown *,_GUID,int)
0x180003ec7  mov     rbx, rax
0x180003eca  test    rax, rax
0x180003ecd  jnz     short loc_180003EED
0x180003ecf  test    byte ptr cs:g_dwDebugFlags, 3
0x180003ed6  jz      short loc_180003F28
0x180003ed8  lea     rax, aAdmSecureDataF_0; "ADM_SECURE_DATA::FindAndReferenceServer"...
0x180003edf  mov     r8d, 222h
0x180003ee5  jmp     short loc_180003F09
0x180003ee7  lock inc dword ptr [rbx+18h]
0x180003eeb  jmp     short loc_180003F28
0x180003eed  lock inc dword ptr [rax+18h]
0x180003ef1  jmp     short loc_180003F28
0x180003ef3  test    byte ptr cs:g_dwDebugFlags, 3
0x180003efa  jz      short loc_180003F28
0x180003efc  lea     rax, aAdmSecureDataF_3; "ADM_SECURE_DATA::FindAndReferenceServer"...
0x180003f03  mov     r8d, 22Eh; unsigned int
0x180003f09  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003f10  lea     r9, aAdmSecureDataF_4; "ADM_SECURE_DATA::FindAndReferenceServer"...
0x180003f17  lea     rdx, aInetsrvIisMbPr; "inetsrv\\iis\\mb\\proxy\\secdat.cxx"
0x180003f1e  mov     [rsp+68h+var_48], rax; char *
0x180003f23  call    PuDbgPrint
0x180003f28  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003f2f  call    cs:__imp_LeaveCriticalSection
0x180003f35  mov     rax, rbx
0x180003f38  mov     rcx, [rsp+68h+var_18]
0x180003f3d  xor     rcx, rsp; StackCookie
0x180003f40  call    __security_check_cookie
0x180003f45  lea     r11, [rsp+68h+var_8]
0x180003f4a  mov     rbx, [r11+18h]
0x180003f4e  mov     rsi, [r11+20h]
0x180003f52  mov     rsp, r11
0x180003f55  pop     rdi
0x180003f56  retn
```
