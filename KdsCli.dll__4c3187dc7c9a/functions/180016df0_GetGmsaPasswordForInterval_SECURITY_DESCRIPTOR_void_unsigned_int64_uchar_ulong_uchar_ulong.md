# _GetGmsaPasswordForInterval(_SECURITY_DESCRIPTOR *,void *,unsigned __int64,uchar * *,ulong *,uchar *,ulong)

- ea: `0x180016df0`
- end: `0x18001702a`
- name: `?_GetGmsaPasswordForInterval@@YAJPEAU_SECURITY_DESCRIPTOR@@PEAX_KPEAPEAEPEAKPEAEK@Z`
- size: `570`
- prototype: `__int64 __usercall@<rax>(struct _SECURITY_DESCRIPTOR *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int64@<r8>, unsigned __int8 **@<r9>, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017300`

## callees

- `0x180010950`
- `0x180016b30`
- `0x180016df0`
- `0x180019274`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e67`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180016e95`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180016e95`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016e5d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016e5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180016eca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180016eca`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016f88`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016f88`
- `api-ms-win-security-base-private-l1-1-0!IsValidRelativeSecurityDescriptor` at `0x180016edd`
- `api-ms-win-security-base-private-l1-1-0!IsValidRelativeSecurityDescriptor` at `0x180016edd`

## string_xrefs

- `0x180016e73`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`
- `0x180016ea5`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`
- `0x180016f62`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`
- `0x180016fd6`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`

## pseudocode

```c
__int64 __fastcall _GetGmsaPasswordForInterval(
        struct _SECURITY_DESCRIPTOR *a1,
        unsigned __int8 *a2,
        unsigned __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  _BYTE *v7; // rdi
  unsigned int v8; // esi
  unsigned __int8 *v13; // r14
  unsigned int v14; // r15d
  DWORD LastError; // eax
  unsigned int v16; // ebx
  unsigned int v17; // r9d
  __int64 SecurityDescriptorLength; // rdi
  signed int KeyFromKdsService; // eax
  DWORD LengthSid; // eax
  signed int GmsaPassword; // eax
  __int64 v22; // rax
  _BYTE *v23; // rcx
  void *lpMem; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v26; // [rsp+D0h] [rbp+8h] BYREF

  v7 = 0;
  v8 = 0;
  lpMem = 0;
  v26 = 0;
  if ( a1 && a4 && a2 && (v13 = a6) != 0 && (v14 = a7) != 0 )
  {
    if ( !IsValidSid(a2) )
    {
      LastError = GetLastError();
      SidKeyDebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx",
        0x114u);
      return (unsigned int)-2147024809;
    }
    if ( !IsValidSecurityDescriptor(a1) )
    {
      v17 = 286;
LABEL_10:
      v16 = -2147024809;
      SidKeyDebugTraceError(0x80070057, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx", v17);
      return v16;
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(a1);
    if ( !(unsigned int)IsValidRelativeSecurityDescriptor(a1, SecurityDescriptorLength, 5) )
    {
      v17 = 299;
      goto LABEL_10;
    }
    KeyFromKdsService = GetKeyFromKdsService(
                          &a1->Revision,
                          SecurityDescriptorLength,
                          0,
                          a3 / 0x14F46B0400000LL,
                          (a3 / 0xA7A35820000LL) & 0x1F,
                          (a3 / 0x53D1AC1000LL) & 0x1F,
                          0,
                          0,
                          0,
                          0,
                          0,
                          (unsigned __int8 **)&lpMem,
                          &v26);
    v16 = KeyFromKdsService;
    if ( KeyFromKdsService >= 0 )
    {
      LengthSid = GetLengthSid(a2);
      v7 = lpMem;
      v8 = v26;
      GmsaPassword = _GenerateGmsaPassword((struct _SID_KEY_HEADER *)lpMem, v26, 0, a2, LengthSid, a4, a5, v13, v14);
      v16 = GmsaPassword;
      if ( GmsaPassword < 0 )
        SidKeyDebugTraceError(
          GmsaPassword,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx",
          0x158u);
    }
    else
    {
      SidKeyDebugTraceError(
        KeyFromKdsService,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx",
        0x147u);
      v7 = lpMem;
      v8 = v26;
    }
  }
  else
  {
    v16 = -2147024809;
  }
  if ( v7 )
  {
    v22 = v8;
    v23 = v7;
    if ( v8 )
    {
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
    }
    SIDKeyProvFree(v7);
  }
  return v16;
}

```

## disassembly

```asm
0x180016df0  mov     rax, rsp
0x180016df3  push    rbx
0x180016df4  push    rbp
0x180016df5  push    rsi
0x180016df6  push    rdi
0x180016df7  push    r12
0x180016df9  push    r13
0x180016dfb  push    r14
0x180016dfd  push    r15
0x180016dff  sub     rsp, 88h
0x180016e06  xor     edi, edi
0x180016e08  xor     esi, esi
0x180016e0a  mov     [rax-58h], rdi
0x180016e0e  mov     r12, r9
0x180016e11  mov     [rax+8], esi
0x180016e14  mov     r13, r8
0x180016e17  mov     rbp, rdx
0x180016e1a  mov     rbx, rcx
0x180016e1d  test    rcx, rcx
0x180016e20  jz      loc_180016FED
0x180016e26  test    r9, r9
0x180016e29  jz      loc_180016FED
0x180016e2f  test    rdx, rdx
0x180016e32  jz      loc_180016FED
0x180016e38  mov     r14, [rsp+0C8h+arg_28]
0x180016e40  test    r14, r14
0x180016e43  jz      loc_180016FED
0x180016e49  mov     r15d, [rsp+0C8h+arg_30]
0x180016e51  test    r15d, r15d
0x180016e54  jz      loc_180016FED
0x180016e5a  mov     rcx, rdx; pSid
0x180016e5d  call    cs:__imp_IsValidSid
0x180016e63  test    eax, eax
0x180016e65  jnz     short loc_180016E92
0x180016e67  call    cs:__imp_GetLastError
0x180016e6d  mov     r9d, 114h; unsigned int
0x180016e73  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180016e7a  mov     ecx, eax; unsigned int
0x180016e7c  lea     rdx, aGetlasterror; "GetLastError()"
0x180016e83  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180016e88  mov     ebx, 80070057h
0x180016e8d  jmp     loc_180017014
0x180016e92  mov     rcx, rbx; pSecurityDescriptor
0x180016e95  call    cs:__imp_IsValidSecurityDescriptor
0x180016e9b  test    eax, eax
0x180016e9d  jnz     short loc_180016EC7
0x180016e9f  mov     r9d, 11Eh; unsigned int
0x180016ea5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180016eac  mov     ecx, 80070057h; unsigned int
0x180016eb1  lea     rdx, aHr; "hr"
0x180016eb8  mov     ebx, 80070057h
0x180016ebd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180016ec2  jmp     loc_180017014
0x180016ec7  mov     rcx, rbx; pSecurityDescriptor
0x180016eca  call    cs:__imp_GetSecurityDescriptorLength
0x180016ed0  mov     r8d, 5
0x180016ed6  mov     rcx, rbx
0x180016ed9  mov     edx, eax
0x180016edb  mov     edi, eax
0x180016edd  call    cs:__imp_IsValidRelativeSecurityDescriptor
0x180016ee3  test    eax, eax
0x180016ee5  jnz     short loc_180016EEF
0x180016ee7  mov     r9d, 12Bh
0x180016eed  jmp     short loc_180016EA5
0x180016eef  xor     edx, edx
0x180016ef1  mov     rcx, 53D1AC1000h
0x180016efb  mov     rax, r13
0x180016efe  xor     r8d, r8d; struct _GUID *
0x180016f01  div     rcx
0x180016f04  lea     rdx, [rsp+0C8h+arg_0]
0x180016f0c  mov     [rsp+0C8h+var_68], rdx; unsigned int *
0x180016f11  mov     ecx, eax
0x180016f13  mov     r9, rax
0x180016f16  lea     rdx, [rsp+0C8h+lpMem]
0x180016f1b  mov     [rsp+0C8h+var_70], rdx; unsigned __int8 **
0x180016f20  and     ecx, 1Fh
0x180016f23  mov     [rsp+0C8h+var_78], rsi; unsigned __int16 *
0x180016f28  mov     edx, edi; unsigned int
0x180016f2a  mov     [rsp+0C8h+var_80], esi; unsigned int
0x180016f2e  mov     [rsp+0C8h+var_88], rsi; unsigned __int16 *
0x180016f33  mov     dword ptr [rsp+0C8h+var_90], esi; unsigned int
0x180016f37  shr     rax, 5
0x180016f3b  mov     dword ptr [rsp+0C8h+var_98], esi; int
0x180016f3f  and     eax, 1Fh
0x180016f42  mov     dword ptr [rsp+0C8h+var_A0], ecx; int
0x180016f46  mov     rcx, rbx; unsigned __int8 *
0x180016f49  shr     r9, 0Ah; int
0x180016f4d  mov     [rsp+0C8h+var_A8], eax; int
0x180016f51  call    ?GetKeyFromKdsService@@YAJPEAEKPEAU_GUID@@JJJHKPEBGK2PEAPEAEPEAK@Z; GetKeyFromKdsService(uchar *,ulong,_GUID *,long,long,long,int,ulong,ushort const *,ulong,ushort const *,uchar * *,ulong *)
0x180016f56  mov     ebx, eax
0x180016f58  test    eax, eax
0x180016f5a  jns     short loc_180016F85
0x180016f5c  mov     r9d, 147h; unsigned int
0x180016f62  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180016f69  lea     rdx, aHr; "hr"
0x180016f70  mov     ecx, eax; unsigned int
0x180016f72  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180016f77  mov     rdi, [rsp+0C8h+lpMem]
0x180016f7c  mov     esi, [rsp+0C8h+arg_0]
0x180016f83  jmp     short loc_180016FF2
0x180016f85  mov     rcx, rbp; pSid
0x180016f88  call    cs:__imp_GetLengthSid
0x180016f8e  mov     rcx, [rsp+0C8h+arg_20]
0x180016f96  mov     r9, rbp; unsigned __int8 *
0x180016f99  mov     rdi, [rsp+0C8h+lpMem]
0x180016f9e  xor     r8d, r8d; struct _KEK_KEY_INFO *
0x180016fa1  mov     esi, [rsp+0C8h+arg_0]
0x180016fa8  mov     edx, esi; unsigned int
0x180016faa  mov     dword ptr [rsp+0C8h+var_88], r15d; unsigned int
0x180016faf  mov     [rsp+0C8h+var_90], r14; unsigned __int8 *
0x180016fb4  mov     [rsp+0C8h+var_98], rcx; unsigned int *
0x180016fb9  mov     rcx, rdi; struct _SID_KEY_HEADER *
0x180016fbc  mov     [rsp+0C8h+var_A0], r12; unsigned __int8 **
0x180016fc1  mov     [rsp+0C8h+var_A8], eax; DWORD
0x180016fc5  call    ?_GenerateGmsaPassword@@YAJQEAEKPEAU_KEK_KEY_INFO@@PEAEKPEAPEAEPEAK2K@Z; _GenerateGmsaPassword(uchar * const,ulong,_KEK_KEY_INFO *,uchar *,ulong,uchar * *,ulong *,uchar *,ulong)
0x180016fca  mov     ebx, eax
0x180016fcc  test    eax, eax
0x180016fce  jns     short loc_180016FF2
0x180016fd0  mov     r9d, 158h; unsigned int
0x180016fd6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180016fdd  lea     rdx, aHr; "hr"
0x180016fe4  mov     ecx, eax; unsigned int
0x180016fe6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180016feb  jmp     short loc_180016FF2
0x180016fed  mov     ebx, 80070057h
0x180016ff2  test    rdi, rdi
0x180016ff5  jz      short loc_180017014
0x180016ff7  mov     eax, esi
0x180016ff9  mov     rcx, rdi
0x180016ffc  test    esi, esi
0x180016ffe  jz      short loc_18001700C
0x180017000  mov     byte ptr [rcx], 0
0x180017003  inc     rcx
0x180017006  sub     rax, 1
0x18001700a  jnz     short loc_180017000
0x18001700c  mov     rcx, rdi; lpMem
0x18001700f  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180017014  mov     eax, ebx
0x180017016  add     rsp, 88h
0x18001701d  pop     r15
0x18001701f  pop     r14
0x180017021  pop     r13
0x180017023  pop     r12
0x180017025  pop     rdi
0x180017026  pop     rsi
0x180017027  pop     rbp
0x180017028  pop     rbx
0x180017029  retn
```
