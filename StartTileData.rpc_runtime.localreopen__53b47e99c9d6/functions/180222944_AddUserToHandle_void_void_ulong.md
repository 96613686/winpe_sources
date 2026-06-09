# AddUserToHandle(void *,void *,ulong)

- ea: `0x180222944`
- end: `0x180222b42`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `510`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180199f90`

## callees

- `0x18001aca4`
- `0x1800a91e8`
- `0x1801b7d08`
- `0x180222944`
- `0x180222b80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222aad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222b02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222aad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222b02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222b23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802229af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222a9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222af4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222b15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802229af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222a9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222af4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222b15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1802229bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1802229bd`
- `ntdll!NtSetSecurityObject` at `0x180222ac7`
- `ntdll!NtSetSecurityObject` at `0x180222ac7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180222a2c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180222a2c`
- `ntdll!NtQuerySecurityObject` at `0x180222977`
- `ntdll!NtQuerySecurityObject` at `0x180222a03`
- `ntdll!NtQuerySecurityObject` at `0x180222977`
- `ntdll!NtQuerySecurityObject` at `0x180222a03`

## string_xrefs

- `0x18022298c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1802229cf`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180222a3f`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180222a7e`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180222ad5`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

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
0x180222944  push    rbp
0x180222946  push    rbx
0x180222947  push    rsi
0x180222948  push    rdi
0x180222949  push    r14
0x18022294b  push    r15
0x18022294d  mov     rbp, rsp
0x180222950  sub     rsp, 68h
0x180222954  xor     r9d, r9d; Length
0x180222957  mov     [rbp+Length], 0
0x18022295e  mov     r14d, r8d
0x180222961  lea     rax, [rbp+Length]
0x180222965  mov     r15, rdx
0x180222968  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x18022296d  xor     r8d, r8d; SecurityDescriptor
0x180222970  mov     rdi, rcx
0x180222973  lea     edx, [r9+4]; SecurityInformation
0x180222977  call    cs:__imp_NtQuerySecurityObject
0x18022297d  cmp     eax, 0C0000023h
0x180222982  jz      short loc_1802229AC
0x180222984  test    eax, eax
0x180222986  jns     short loc_1802229A5
0x180222988  mov     rcx, [rbp+30h]; this
0x18022298c  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222993  mov     r9d, eax; char *
0x180222996  mov     edx, 62h ; 'b'; void *
0x18022299b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802229a0  jmp     loc_180222B35
0x1802229a5  xor     eax, eax
0x1802229a7  jmp     loc_180222B35
0x1802229ac  mov     ebx, [rbp+Length]
0x1802229af  call    cs:__imp_GetProcessHeap
0x1802229b5  mov     r8d, ebx; dwBytes
0x1802229b8  xor     edx, edx; dwFlags
0x1802229ba  mov     rcx, rax; hHeap
0x1802229bd  call    cs:__imp_HeapAlloc
0x1802229c3  mov     rsi, rax
0x1802229c6  test    rax, rax
0x1802229c9  jnz     short loc_1802229EB
0x1802229cb  mov     rcx, [rbp+30h]; this
0x1802229cf  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1802229d6  mov     ebx, 8007000Eh
0x1802229db  lea     edx, [rax+66h]; void *
0x1802229de  mov     r9d, ebx; char *
0x1802229e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802229e6  jmp     loc_180222B33
0x1802229eb  mov     r9d, [rbp+Length]; Length
0x1802229ef  lea     rax, [rbp+Length]
0x1802229f3  mov     r8, rsi; SecurityDescriptor
0x1802229f6  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x1802229fb  mov     edx, 4; SecurityInformation
0x180222a00  mov     rcx, rdi; Handle
0x180222a03  call    cs:__imp_NtQuerySecurityObject
0x180222a09  test    eax, eax
0x180222a0b  jns     short loc_180222A14
0x180222a0d  mov     edx, 69h ; 'i'
0x180222a12  jmp     short loc_180222A3B
0x180222a14  xor     eax, eax
0x180222a16  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180222a1a  xorps   xmm0, xmm0
0x180222a1d  mov     [rbp+lpMem], rax
0x180222a21  movups  [rbp+SecurityDescriptor], xmm0
0x180222a25  lea     edx, [rax+1]; Revision
0x180222a28  movups  [rbp+var_20], xmm0
0x180222a2c  call    cs:__imp_RtlCreateSecurityDescriptor
0x180222a32  test    eax, eax
0x180222a34  jns     short loc_180222A55
0x180222a36  mov     edx, 6Ch ; 'l'; void *
0x180222a3b  mov     rcx, [rbp+30h]; this
0x180222a3f  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222a46  mov     r9d, eax; char *
0x180222a49  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180222a4e  mov     ebx, eax
0x180222a50  jmp     loc_180222B2B
0x180222a55  lea     rax, [rbp+SecurityDescriptor]
0x180222a59  mov     [rbp+arg_18], 0
0x180222a5d  lea     r9, [rbp+arg_18]; bool *
0x180222a61  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180222a66  mov     r8d, r14d; unsigned int
0x180222a69  mov     rdx, r15; void *
0x180222a6c  mov     rcx, rsi; void *
0x180222a6f  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x180222a74  mov     ebx, eax
0x180222a76  test    eax, eax
0x180222a78  jns     short loc_180222AB5
0x180222a7a  mov     rcx, [rbp+30h]; this
0x180222a7e  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222a85  mov     r9d, eax; char *
0x180222a88  mov     edx, 72h ; 'r'; void *
0x180222a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180222a92  mov     rdi, [rbp+lpMem]
0x180222a96  test    rdi, rdi
0x180222a99  jz      loc_180222B2B
0x180222a9f  call    cs:__imp_GetProcessHeap
0x180222aa5  mov     r8, rdi; lpMem
0x180222aa8  xor     edx, edx; dwFlags
0x180222aaa  mov     rcx, rax; hHeap
0x180222aad  call    cs:__imp_HeapFree
0x180222ab3  jmp     short loc_180222B2B
0x180222ab5  cmp     [rbp+arg_18], 0
0x180222ab9  jnz     short loc_180222B0C
0x180222abb  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180222abf  mov     edx, 4; SecurityInformation
0x180222ac4  mov     rcx, rdi; Handle
0x180222ac7  call    cs:__imp_NtSetSecurityObject
0x180222acd  test    eax, eax
0x180222acf  jns     short loc_180222B0C
0x180222ad1  mov     rcx, [rbp+30h]; this
0x180222ad5  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222adc  mov     r9d, eax; char *
0x180222adf  mov     edx, 79h ; 'y'; void *
0x180222ae4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180222ae9  mov     rbx, [rbp+lpMem]
0x180222aed  mov     edi, eax
0x180222aef  test    rbx, rbx
0x180222af2  jz      short loc_180222B08
0x180222af4  call    cs:__imp_GetProcessHeap
0x180222afa  mov     r8, rbx; lpMem
0x180222afd  xor     edx, edx; dwFlags
0x180222aff  mov     rcx, rax; hHeap
0x180222b02  call    cs:__imp_HeapFree
0x180222b08  mov     ebx, edi
0x180222b0a  jmp     short loc_180222B2B
0x180222b0c  mov     rbx, [rbp+lpMem]
0x180222b10  test    rbx, rbx
0x180222b13  jz      short loc_180222B29
0x180222b15  call    cs:__imp_GetProcessHeap
0x180222b1b  mov     r8, rbx; lpMem
0x180222b1e  xor     edx, edx; dwFlags
0x180222b20  mov     rcx, rax; hHeap
0x180222b23  call    cs:__imp_HeapFree
0x180222b29  xor     ebx, ebx
0x180222b2b  mov     rcx, rsi; this
0x180222b2e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180222b33  mov     eax, ebx
0x180222b35  add     rsp, 68h
0x180222b39  pop     r15
0x180222b3b  pop     r14
0x180222b3d  pop     rdi
0x180222b3e  pop     rsi
0x180222b3f  pop     rbx
0x180222b40  pop     rbp
0x180222b41  retn
```
