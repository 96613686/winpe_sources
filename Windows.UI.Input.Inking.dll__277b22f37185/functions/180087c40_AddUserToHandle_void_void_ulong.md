# AddUserToHandle(void *,void *,ulong)

- ea: `0x180087c40`
- end: `0x180087e3e`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `510`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180087e44`

## callees

- `0x18000e66c`
- `0x18001332c`
- `0x180087c40`
- `0x180087f7c`
- `0x180089030`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087cab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087d9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087df0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087cab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087d9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087df0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087e11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087da9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087dfe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087da9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087dfe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087e1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087cb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087cb9`
- `ntdll!NtSetSecurityObject` at `0x180087dc3`
- `ntdll!NtSetSecurityObject` at `0x180087dc3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180087d28`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180087d28`
- `ntdll!NtQuerySecurityObject` at `0x180087c73`
- `ntdll!NtQuerySecurityObject` at `0x180087cff`
- `ntdll!NtQuerySecurityObject` at `0x180087c73`
- `ntdll!NtQuerySecurityObject` at `0x180087cff`

## string_xrefs

- `0x180087c88`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087ccb`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087d3b`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087d7a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087dd1`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall AddUserToHandle(HANDLE Handle, void *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  ULONG v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  int v11; // ebx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdi
  HANDLE v17; // rax
  NTSTATUS v18; // eax
  int v19; // eax
  void *v20; // rbx
  int v21; // edi
  HANDLE v22; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  int LengthNeeded; // [rsp+20h] [rbp-48h]
  int LengthNeededa; // [rsp+20h] [rbp-48h]
  int LengthNeededb; // [rsp+20h] [rbp-48h]
  ULONG Length; // [rsp+30h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  bool v32; // [rsp+B8h] [rbp+50h] BYREF

  Length = 0;
  v6 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v6 == -1073741789 )
  {
    v8 = Length;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 0, v8);
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
    if ( v12 >= 0 )
    {
      lpMem = 0;
      memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      v12 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v12 >= 0 )
      {
        v32 = 0;
        v15 = BuildUserSD(v10, a2, a3, &v32, SecurityDescriptor);
        v11 = v15;
        if ( v15 >= 0 )
        {
          if ( v32 || (v18 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor), v18 >= 0) )
          {
            v23 = lpMem;
            if ( lpMem )
            {
              v24 = GetProcessHeap();
              HeapFree(v24, 0, v23);
            }
            v11 = 0;
          }
          else
          {
            v19 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x79,
                    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                    (const char *)(unsigned int)v18,
                    LengthNeededb);
            v20 = lpMem;
            v21 = v19;
            if ( lpMem )
            {
              v22 = GetProcessHeap();
              HeapFree(v22, 0, v20);
            }
            v11 = v21;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x72,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v15,
            LengthNeededb);
          v16 = lpMem;
          if ( lpMem )
          {
            v17 = GetProcessHeap();
            HeapFree(v17, 0, v16);
          }
        }
        goto LABEL_23;
      }
      v13 = 108;
    }
    else
    {
      v13 = 105;
    }
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v12,
            LengthNeededa);
LABEL_23:
    wil::details::FreeProcessHeap((wil::details *)v10, v14);
    return v11;
  }
  if ( v6 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x62,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)v6,
             LengthNeeded);
}

```

## disassembly

```asm
0x180087c40  push    rbp
0x180087c42  push    rbx
0x180087c43  push    rsi
0x180087c44  push    rdi
0x180087c45  push    r14
0x180087c47  push    r15
0x180087c49  mov     rbp, rsp
0x180087c4c  sub     rsp, 68h
0x180087c50  xor     r9d, r9d; Length
0x180087c53  mov     [rbp+Length], 0
0x180087c5a  mov     r14d, r8d
0x180087c5d  lea     rax, [rbp+Length]
0x180087c61  mov     r15, rdx
0x180087c64  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180087c69  xor     r8d, r8d; SecurityDescriptor
0x180087c6c  mov     rdi, rcx
0x180087c6f  lea     edx, [r9+4]; SecurityInformation
0x180087c73  call    cs:__imp_NtQuerySecurityObject
0x180087c79  cmp     eax, 0C0000023h
0x180087c7e  jz      short loc_180087CA8
0x180087c80  test    eax, eax
0x180087c82  jns     short loc_180087CA1
0x180087c84  mov     rcx, [rbp+30h]; this
0x180087c88  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087c8f  mov     r9d, eax; char *
0x180087c92  mov     edx, 62h ; 'b'; void *
0x180087c97  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180087c9c  jmp     loc_180087E31
0x180087ca1  xor     eax, eax
0x180087ca3  jmp     loc_180087E31
0x180087ca8  mov     ebx, [rbp+Length]
0x180087cab  call    cs:__imp_GetProcessHeap
0x180087cb1  mov     r8d, ebx; dwBytes
0x180087cb4  xor     edx, edx; dwFlags
0x180087cb6  mov     rcx, rax; hHeap
0x180087cb9  call    cs:__imp_HeapAlloc
0x180087cbf  mov     rsi, rax
0x180087cc2  test    rax, rax
0x180087cc5  jnz     short loc_180087CE7
0x180087cc7  mov     rcx, [rbp+30h]; this
0x180087ccb  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087cd2  mov     ebx, 8007000Eh
0x180087cd7  lea     edx, [rax+66h]; void *
0x180087cda  mov     r9d, ebx; char *
0x180087cdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087ce2  jmp     loc_180087E2F
0x180087ce7  mov     r9d, [rbp+Length]; Length
0x180087ceb  lea     rax, [rbp+Length]
0x180087cef  mov     r8, rsi; SecurityDescriptor
0x180087cf2  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180087cf7  mov     edx, 4; SecurityInformation
0x180087cfc  mov     rcx, rdi; Handle
0x180087cff  call    cs:__imp_NtQuerySecurityObject
0x180087d05  test    eax, eax
0x180087d07  jns     short loc_180087D10
0x180087d09  mov     edx, 69h ; 'i'
0x180087d0e  jmp     short loc_180087D37
0x180087d10  xor     eax, eax
0x180087d12  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180087d16  xorps   xmm0, xmm0
0x180087d19  mov     [rbp+lpMem], rax
0x180087d1d  movups  [rbp+SecurityDescriptor], xmm0
0x180087d21  lea     edx, [rax+1]; Revision
0x180087d24  movups  [rbp+var_20], xmm0
0x180087d28  call    cs:__imp_RtlCreateSecurityDescriptor
0x180087d2e  test    eax, eax
0x180087d30  jns     short loc_180087D51
0x180087d32  mov     edx, 6Ch ; 'l'; void *
0x180087d37  mov     rcx, [rbp+30h]; this
0x180087d3b  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087d42  mov     r9d, eax; char *
0x180087d45  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180087d4a  mov     ebx, eax
0x180087d4c  jmp     loc_180087E27
0x180087d51  lea     rax, [rbp+SecurityDescriptor]
0x180087d55  mov     [rbp+arg_18], 0
0x180087d59  lea     r9, [rbp+arg_18]; bool *
0x180087d5d  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180087d62  mov     r8d, r14d; unsigned int
0x180087d65  mov     rdx, r15; void *
0x180087d68  mov     rcx, rsi; void *
0x180087d6b  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x180087d70  mov     ebx, eax
0x180087d72  test    eax, eax
0x180087d74  jns     short loc_180087DB1
0x180087d76  mov     rcx, [rbp+30h]; this
0x180087d7a  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087d81  mov     r9d, eax; char *
0x180087d84  mov     edx, 72h ; 'r'; void *
0x180087d89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087d8e  mov     rdi, [rbp+lpMem]
0x180087d92  test    rdi, rdi
0x180087d95  jz      loc_180087E27
0x180087d9b  call    cs:__imp_GetProcessHeap
0x180087da1  mov     r8, rdi; lpMem
0x180087da4  xor     edx, edx; dwFlags
0x180087da6  mov     rcx, rax; hHeap
0x180087da9  call    cs:__imp_HeapFree
0x180087daf  jmp     short loc_180087E27
0x180087db1  cmp     [rbp+arg_18], 0
0x180087db5  jnz     short loc_180087E08
0x180087db7  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180087dbb  mov     edx, 4; SecurityInformation
0x180087dc0  mov     rcx, rdi; Handle
0x180087dc3  call    cs:__imp_NtSetSecurityObject
0x180087dc9  test    eax, eax
0x180087dcb  jns     short loc_180087E08
0x180087dcd  mov     rcx, [rbp+30h]; this
0x180087dd1  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087dd8  mov     r9d, eax; char *
0x180087ddb  mov     edx, 79h ; 'y'; void *
0x180087de0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180087de5  mov     rbx, [rbp+lpMem]
0x180087de9  mov     edi, eax
0x180087deb  test    rbx, rbx
0x180087dee  jz      short loc_180087E04
0x180087df0  call    cs:__imp_GetProcessHeap
0x180087df6  mov     r8, rbx; lpMem
0x180087df9  xor     edx, edx; dwFlags
0x180087dfb  mov     rcx, rax; hHeap
0x180087dfe  call    cs:__imp_HeapFree
0x180087e04  mov     ebx, edi
0x180087e06  jmp     short loc_180087E27
0x180087e08  mov     rbx, [rbp+lpMem]
0x180087e0c  test    rbx, rbx
0x180087e0f  jz      short loc_180087E25
0x180087e11  call    cs:__imp_GetProcessHeap
0x180087e17  mov     r8, rbx; lpMem
0x180087e1a  xor     edx, edx; dwFlags
0x180087e1c  mov     rcx, rax; hHeap
0x180087e1f  call    cs:__imp_HeapFree
0x180087e25  xor     ebx, ebx
0x180087e27  mov     rcx, rsi; this
0x180087e2a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180087e2f  mov     eax, ebx
0x180087e31  add     rsp, 68h
0x180087e35  pop     r15
0x180087e37  pop     r14
0x180087e39  pop     rdi
0x180087e3a  pop     rsi
0x180087e3b  pop     rbx
0x180087e3c  pop     rbp
0x180087e3d  retn
```
