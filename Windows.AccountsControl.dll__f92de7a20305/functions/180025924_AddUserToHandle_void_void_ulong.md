# AddUserToHandle(void *,void *,ulong)

- ea: `0x180025924`
- end: `0x180025ba1`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `637`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025ba8`

## callees

- `0x18000556c`
- `0x180006eac`
- `0x180025924`
- `0x180025d20`
- `0x18002b724`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x18002595c`
- `ntdll!NtQuerySecurityObject` at `0x1800259ec`
- `ntdll!NtQuerySecurityObject` at `0x18002595c`
- `ntdll!NtQuerySecurityObject` at `0x1800259ec`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180025a33`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180025a33`
- `ntdll!NtSetSecurityObject` at `0x180025b19`
- `ntdll!NtSetSecurityObject` at `0x180025b19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002599f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002599f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025ac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025ac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025991`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025ab8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025aea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025991`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025ab8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025aea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b71`

## string_xrefs

- `0x180025978`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800259bd`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800259fd`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025a44`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025a9d`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025b2a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall AddUserToHandle(HANDLE Handle, void *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  ULONG v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rdi
  int v11; // ebx
  NTSTATUS v12; // eax
  void *v13; // rdx
  NTSTATUS v14; // eax
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  void *v18; // rdx
  void *v19; // rsi
  HANDLE v20; // rax
  void *v21; // rbx
  HANDLE v22; // rax
  NTSTATUS v23; // eax
  void *v24; // rdx
  int v25; // esi
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  int LengthNeeded; // [rsp+20h] [rbp-39h]
  int LengthNeededa; // [rsp+20h] [rbp-39h]
  int LengthNeededb; // [rsp+20h] [rbp-39h]
  ULONG Length; // [rsp+30h] [rbp-29h] BYREF
  void *v34; // [rsp+38h] [rbp-21h]
  _OWORD *v35; // [rsp+40h] [rbp-19h]
  char v36; // [rsp+48h] [rbp-11h]
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-9h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  bool v40; // [rsp+D8h] [rbp+7Fh] BYREF

  Length = 0;
  v6 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v6 != -1073741789 )
  {
    if ( v6 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x62,
               (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
               (const char *)(unsigned int)v6,
               LengthNeeded);
    return 0;
  }
  v8 = Length;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, v8);
  v34 = v10;
  if ( !v10 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8007000ELL,
      LengthNeeded);
    return v11;
  }
  v12 = NtQuerySecurityObject(Handle, 4u, v10, Length, &Length);
  if ( v12 < 0 )
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x69,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v12,
            LengthNeededa);
    wil::details::FreeProcessHeap((wil::details *)v10, v13);
    return v11;
  }
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  lpMem = 0;
  v14 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v14 < 0 )
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x6C,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v14,
            LengthNeededa);
    wil::details::FreeProcessHeap((wil::details *)v10, v15);
    return v11;
  }
  v35 = SecurityDescriptor;
  v36 = 1;
  v40 = 0;
  v16 = BuildUserSD(v10, a2, a3, &v40, SecurityDescriptor);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)(unsigned int)v16,
      LengthNeededb);
    v19 = lpMem;
    if ( lpMem )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v19);
    }
    wil::details::FreeProcessHeap((wil::details *)v10, v18);
    return v11;
  }
  if ( v40 )
  {
    v21 = lpMem;
    if ( lpMem )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v21);
    }
LABEL_25:
    wil::details::FreeProcessHeap((wil::details *)v10, v17);
    return 0;
  }
  v23 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
  if ( v23 >= 0 )
  {
    v28 = lpMem;
    if ( lpMem )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
    goto LABEL_25;
  }
  v25 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x79,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
          (const char *)(unsigned int)v23,
          LengthNeededb);
  v26 = lpMem;
  if ( lpMem )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
  wil::details::FreeProcessHeap((wil::details *)v10, v24);
  return v25;
}

```

## disassembly

```asm
0x180025924  push    rbp
0x180025926  push    rbx
0x180025927  push    rsi
0x180025928  push    rdi
0x180025929  push    r14
0x18002592b  push    r15
0x18002592d  lea     rbp, [rsp-2Fh]
0x180025932  sub     rsp, 88h
0x180025939  mov     r14d, r8d
0x18002593c  mov     r15, rdx
0x18002593f  mov     rsi, rcx
0x180025942  mov     [rbp+57h+Length], 0
0x180025949  lea     rax, [rbp+57h+Length]
0x18002594d  mov     qword ptr [rsp+0B0h+LengthNeeded], rax; int
0x180025952  xor     r9d, r9d; Length
0x180025955  xor     r8d, r8d; SecurityDescriptor
0x180025958  lea     edx, [r9+4]; SecurityInformation
0x18002595c  call    cs:__imp_NtQuerySecurityObject
0x180025962  cmp     eax, 0C0000023h
0x180025967  jz      short loc_18002598E
0x180025969  test    eax, eax
0x18002596b  jns     loc_180025B8F
0x180025971  mov     rcx, [rbp+5Fh]; this
0x180025975  mov     r9d, eax; char *
0x180025978  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18002597f  mov     edx, 62h ; 'b'; void *
0x180025984  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025989  jmp     loc_180025B91
0x18002598e  mov     ebx, [rbp+57h+Length]
0x180025991  call    cs:__imp_GetProcessHeap
0x180025997  mov     r8d, ebx; dwBytes
0x18002599a  xor     edx, edx; dwFlags
0x18002599c  mov     rcx, rax; hHeap
0x18002599f  call    cs:__imp_HeapAlloc
0x1800259a5  mov     rdi, rax
0x1800259a8  mov     [rbp+57h+var_78], rax
0x1800259ac  test    rax, rax
0x1800259af  jnz     short loc_1800259D4
0x1800259b1  mov     rcx, [rbp+5Fh]; this
0x1800259b5  mov     ebx, 8007000Eh
0x1800259ba  mov     r9d, ebx; char *
0x1800259bd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800259c4  lea     edx, [rax+66h]; void *
0x1800259c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259cc  nop
0x1800259cd  mov     eax, ebx
0x1800259cf  jmp     loc_180025B91
0x1800259d4  lea     rax, [rbp+57h+Length]
0x1800259d8  mov     qword ptr [rsp+0B0h+LengthNeeded], rax; int
0x1800259dd  mov     r9d, [rbp+57h+Length]; Length
0x1800259e1  mov     r8, rdi; SecurityDescriptor
0x1800259e4  mov     edx, 4; SecurityInformation
0x1800259e9  mov     rcx, rsi; Handle
0x1800259ec  call    cs:__imp_NtQuerySecurityObject
0x1800259f2  test    eax, eax
0x1800259f4  jns     short loc_180025A1B
0x1800259f6  mov     rcx, [rbp+5Fh]; this
0x1800259fa  mov     r9d, eax; char *
0x1800259fd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025a04  mov     edx, 69h ; 'i'; void *
0x180025a09  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025a0e  mov     ebx, eax
0x180025a10  mov     rcx, rdi; this
0x180025a13  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025a18  nop
0x180025a19  jmp     short loc_1800259CD
0x180025a1b  xorps   xmm0, xmm0
0x180025a1e  xor     eax, eax
0x180025a20  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180025a24  movups  [rbp+57h+var_50], xmm0
0x180025a28  mov     [rbp+57h+lpMem], rax
0x180025a2c  lea     edx, [rax+1]; Revision
0x180025a2f  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180025a33  call    cs:__imp_RtlCreateSecurityDescriptor
0x180025a39  test    eax, eax
0x180025a3b  jns     short loc_180025A65
0x180025a3d  mov     rcx, [rbp+5Fh]; this
0x180025a41  mov     r9d, eax; char *
0x180025a44  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025a4b  mov     edx, 6Ch ; 'l'; void *
0x180025a50  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025a55  mov     ebx, eax
0x180025a57  mov     rcx, rdi; this
0x180025a5a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025a5f  nop
0x180025a60  jmp     loc_1800259CD
0x180025a65  lea     rax, [rbp+57h+SecurityDescriptor]
0x180025a69  mov     [rbp+57h+var_70], rax
0x180025a6d  mov     [rbp+57h+var_68], 1
0x180025a71  mov     [rbp+57h+arg_18], 0
0x180025a75  lea     rax, [rbp+57h+SecurityDescriptor]
0x180025a79  mov     qword ptr [rsp+0B0h+LengthNeeded], rax; int
0x180025a7e  lea     r9, [rbp+57h+arg_18]; bool *
0x180025a82  mov     r8d, r14d; unsigned int
0x180025a85  mov     rdx, r15; void *
0x180025a88  mov     rcx, rdi; void *
0x180025a8b  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x180025a90  mov     ebx, eax
0x180025a92  test    eax, eax
0x180025a94  jns     short loc_180025ADB
0x180025a96  mov     rcx, [rbp+5Fh]; this
0x180025a9a  mov     r9d, eax; char *
0x180025a9d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025aa4  mov     edx, 72h ; 'r'; void *
0x180025aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025aae  nop
0x180025aaf  mov     rsi, [rbp+57h+lpMem]
0x180025ab3  test    rsi, rsi
0x180025ab6  jz      short loc_180025ACD
0x180025ab8  call    cs:__imp_GetProcessHeap
0x180025abe  mov     r8, rsi; lpMem
0x180025ac1  xor     edx, edx; dwFlags
0x180025ac3  mov     rcx, rax; hHeap
0x180025ac6  call    cs:__imp_HeapFree
0x180025acc  nop
0x180025acd  mov     rcx, rdi; this
0x180025ad0  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025ad5  nop
0x180025ad6  jmp     loc_1800259CD
0x180025adb  cmp     [rbp+57h+arg_18], 0
0x180025adf  jz      short loc_180025B0D
0x180025ae1  mov     rbx, [rbp+57h+lpMem]
0x180025ae5  test    rbx, rbx
0x180025ae8  jz      short loc_180025AFF
0x180025aea  call    cs:__imp_GetProcessHeap
0x180025af0  mov     r8, rbx; lpMem
0x180025af3  xor     edx, edx; dwFlags
0x180025af5  mov     rcx, rax; hHeap
0x180025af8  call    cs:__imp_HeapFree
0x180025afe  nop
0x180025aff  mov     rcx, rdi; this
0x180025b02  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025b07  nop
0x180025b08  jmp     loc_180025B8F
0x180025b0d  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180025b11  mov     edx, 4; SecurityInformation
0x180025b16  mov     rcx, rsi; Handle
0x180025b19  call    cs:__imp_NtSetSecurityObject
0x180025b1f  test    eax, eax
0x180025b21  jns     short loc_180025B68
0x180025b23  mov     rcx, [rbp+5Fh]; this
0x180025b27  mov     r9d, eax; char *
0x180025b2a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025b31  mov     edx, 79h ; 'y'; void *
0x180025b36  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025b3b  mov     esi, eax
0x180025b3d  mov     rbx, [rbp+57h+lpMem]
0x180025b41  test    rbx, rbx
0x180025b44  jz      short loc_180025B5B
0x180025b46  call    cs:__imp_GetProcessHeap
0x180025b4c  mov     r8, rbx; lpMem
0x180025b4f  xor     edx, edx; dwFlags
0x180025b51  mov     rcx, rax; hHeap
0x180025b54  call    cs:__imp_HeapFree
0x180025b5a  nop
0x180025b5b  mov     rcx, rdi; this
0x180025b5e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025b63  nop
0x180025b64  mov     eax, esi
0x180025b66  jmp     short loc_180025B91
0x180025b68  mov     rbx, [rbp+57h+lpMem]
0x180025b6c  test    rbx, rbx
0x180025b6f  jz      short loc_180025B86
0x180025b71  call    cs:__imp_GetProcessHeap
0x180025b77  mov     r8, rbx; lpMem
0x180025b7a  xor     edx, edx; dwFlags
0x180025b7c  mov     rcx, rax; hHeap
0x180025b7f  call    cs:__imp_HeapFree
0x180025b85  nop
0x180025b86  mov     rcx, rdi; this
0x180025b89  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025b8e  nop
0x180025b8f  xor     eax, eax
0x180025b91  add     rsp, 88h
0x180025b98  pop     r15
0x180025b9a  pop     r14
0x180025b9c  pop     rdi
0x180025b9d  pop     rsi
0x180025b9e  pop     rbx
0x180025b9f  pop     rbp
0x180025ba0  retn
```
