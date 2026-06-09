# ImpersonateForCertAccess(ushort const *)

- ea: `0x180093398`
- end: `0x1800934ac`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180092d8c`

## callees

- `0x180004d50`
- `0x180093398`

## import_xrefs

- `DMCmnUtils!DmImpersonate` at `0x18009343f`
- `DMCmnUtils!DmImpersonate` at `0x18009343f`
- `DMCmnUtils!InvStrCmpIW` at `0x180093414`
- `DMCmnUtils!InvStrCmpIW` at `0x180093414`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093469`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093469`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093486`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009345b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180093478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009345b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180093478`
- `RPCRT4!UuidFromStringW` at `0x1800933d3`
- `RPCRT4!UuidFromStringW` at `0x1800933d3`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1800933f5`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1800933f5`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18009342f`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18009342f`

## pseudocode

```c
__int64 __fastcall ImpersonateForCertAccess(unsigned __int16 *a1)
{
  int EnrollmentCertStore; // ebx
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-40h] BYREF
  LPVOID v8; // [rsp+28h] [rbp-38h] BYREF
  UUID v9; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  lpMem = 0;
  v8 = 0;
  Uuid = 0;
  if ( UuidFromStringW(a1, &Uuid) )
  {
    EnrollmentCertStore = -2147024809;
  }
  else
  {
    v9 = Uuid;
    EnrollmentCertStore = GetEnrollmentCertStore(&v9, &v8);
    if ( EnrollmentCertStore >= 0 )
    {
      if ( v8 )
      {
        if ( !InvStrCmpIW((const unsigned __int16 *)v8, L"User") )
        {
          v9 = Uuid;
          EnrollmentCertStore = GetEnrollmentSID(&v9, &lpMem);
          if ( EnrollmentCertStore >= 0 )
          {
            EnrollmentCertStore = DmImpersonate((const unsigned __int16 *)lpMem);
            if ( EnrollmentCertStore >= 0 )
              byte_1800FB484 = 1;
          }
        }
      }
    }
  }
  v2 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = v8;
  if ( v8 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  return (unsigned int)EnrollmentCertStore;
}

```

## disassembly

```asm
0x180093398  mov     [rsp-8+arg_8], rbx
0x18009339d  mov     [rsp-8+arg_10], rdi
0x1800933a2  push    rbp
0x1800933a3  mov     rbp, rsp
0x1800933a6  sub     rsp, 60h
0x1800933aa  mov     rax, cs:__security_cookie
0x1800933b1  xor     rax, rsp
0x1800933b4  mov     [rbp+var_10], rax
0x1800933b8  xorps   xmm0, xmm0
0x1800933bb  mov     [rbp+lpMem], 0
0x1800933c3  lea     rdx, [rbp+Uuid]; Uuid
0x1800933c7  mov     [rbp+var_38], 0
0x1800933cf  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800933d3  call    cs:__imp_UuidFromStringW
0x1800933d9  test    eax, eax
0x1800933db  jz      short loc_1800933E4
0x1800933dd  mov     ebx, 80070057h
0x1800933e2  jmp     short loc_180093452
0x1800933e4  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1800933e8  lea     rdx, [rbp+var_38]
0x1800933ec  lea     rcx, [rbp+var_30]
0x1800933f0  movdqa  [rbp+var_30], xmm0
0x1800933f5  call    cs:__imp_GetEnrollmentCertStore
0x1800933fb  mov     ebx, eax
0x1800933fd  test    eax, eax
0x1800933ff  js      short loc_180093452
0x180093401  mov     rdi, [rbp+var_38]
0x180093405  test    rdi, rdi
0x180093408  jz      short loc_180093452
0x18009340a  lea     rdx, aUser_0; "User"
0x180093411  mov     rcx, rdi
0x180093414  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18009341a  test    eax, eax
0x18009341c  jnz     short loc_180093452
0x18009341e  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180093422  lea     rdx, [rbp+lpMem]
0x180093426  lea     rcx, [rbp+var_30]
0x18009342a  movdqa  [rbp+var_30], xmm0
0x18009342f  call    cs:__imp_GetEnrollmentSID
0x180093435  mov     ebx, eax
0x180093437  test    eax, eax
0x180093439  js      short loc_180093452
0x18009343b  mov     rcx, [rbp+lpMem]
0x18009343f  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180093445  mov     ebx, eax
0x180093447  test    eax, eax
0x180093449  js      short loc_180093452
0x18009344b  mov     cs:byte_1800FB484, 1
0x180093452  mov     rdi, [rbp+lpMem]
0x180093456  test    rdi, rdi
0x180093459  jz      short loc_18009346F
0x18009345b  call    cs:__imp_GetProcessHeap
0x180093461  mov     r8, rdi; lpMem
0x180093464  xor     edx, edx; dwFlags
0x180093466  mov     rcx, rax; hHeap
0x180093469  call    cs:__imp_HeapFree
0x18009346f  mov     rdi, [rbp+var_38]
0x180093473  test    rdi, rdi
0x180093476  jz      short loc_18009348C
0x180093478  call    cs:__imp_GetProcessHeap
0x18009347e  mov     r8, rdi; lpMem
0x180093481  xor     edx, edx; dwFlags
0x180093483  mov     rcx, rax; hHeap
0x180093486  call    cs:__imp_HeapFree
0x18009348c  mov     eax, ebx
0x18009348e  mov     rcx, [rbp+var_10]
0x180093492  xor     rcx, rsp; StackCookie
0x180093495  call    __security_check_cookie
0x18009349a  lea     r11, [rsp+60h+var_s0]
0x18009349f  mov     rbx, [r11+18h]
0x1800934a3  mov     rdi, [r11+20h]
0x1800934a7  mov     rsp, r11
0x1800934aa  pop     rbp
0x1800934ab  retn
```
