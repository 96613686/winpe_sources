# ImpersonateForCertAccess(ushort const *)

- ea: `0x140051c68`
- end: `0x140051d7c`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400516ec`

## callees

- `0x1400042f0`
- `0x140051c68`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentCertStore` at `0x140051cc5`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x140051cc5`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140051cff`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140051cff`
- `DMCmnUtils!InvStrCmpIW` at `0x140051ce4`
- `DMCmnUtils!InvStrCmpIW` at `0x140051ce4`
- `DMCmnUtils!DmImpersonate` at `0x140051d0f`
- `DMCmnUtils!DmImpersonate` at `0x140051d0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140051d39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140051d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140051d39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140051d56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051d2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051d2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051d48`
- `RPCRT4!UuidFromStringW` at `0x140051ca3`
- `RPCRT4!UuidFromStringW` at `0x140051ca3`

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
              byte_14007E5F8 = 1;
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
0x140051c68  mov     [rsp-8+arg_8], rbx
0x140051c6d  mov     [rsp-8+arg_10], rdi
0x140051c72  push    rbp
0x140051c73  mov     rbp, rsp
0x140051c76  sub     rsp, 60h
0x140051c7a  mov     rax, cs:__security_cookie
0x140051c81  xor     rax, rsp
0x140051c84  mov     [rbp+var_10], rax
0x140051c88  xorps   xmm0, xmm0
0x140051c8b  mov     [rbp+lpMem], 0
0x140051c93  lea     rdx, [rbp+Uuid]; Uuid
0x140051c97  mov     [rbp+var_38], 0
0x140051c9f  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x140051ca3  call    cs:__imp_UuidFromStringW
0x140051ca9  test    eax, eax
0x140051cab  jz      short loc_140051CB4
0x140051cad  mov     ebx, 80070057h
0x140051cb2  jmp     short loc_140051D22
0x140051cb4  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x140051cb8  lea     rdx, [rbp+var_38]
0x140051cbc  lea     rcx, [rbp+var_30]
0x140051cc0  movdqa  [rbp+var_30], xmm0
0x140051cc5  call    cs:__imp_GetEnrollmentCertStore
0x140051ccb  mov     ebx, eax
0x140051ccd  test    eax, eax
0x140051ccf  js      short loc_140051D22
0x140051cd1  mov     rdi, [rbp+var_38]
0x140051cd5  test    rdi, rdi
0x140051cd8  jz      short loc_140051D22
0x140051cda  lea     rdx, aUser; "User"
0x140051ce1  mov     rcx, rdi
0x140051ce4  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x140051cea  test    eax, eax
0x140051cec  jnz     short loc_140051D22
0x140051cee  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x140051cf2  lea     rdx, [rbp+lpMem]
0x140051cf6  lea     rcx, [rbp+var_30]
0x140051cfa  movdqa  [rbp+var_30], xmm0
0x140051cff  call    cs:__imp_GetEnrollmentSID
0x140051d05  mov     ebx, eax
0x140051d07  test    eax, eax
0x140051d09  js      short loc_140051D22
0x140051d0b  mov     rcx, [rbp+lpMem]
0x140051d0f  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x140051d15  mov     ebx, eax
0x140051d17  test    eax, eax
0x140051d19  js      short loc_140051D22
0x140051d1b  mov     cs:byte_14007E5F8, 1
0x140051d22  mov     rdi, [rbp+lpMem]
0x140051d26  test    rdi, rdi
0x140051d29  jz      short loc_140051D3F
0x140051d2b  call    cs:__imp_GetProcessHeap
0x140051d31  mov     r8, rdi; lpMem
0x140051d34  xor     edx, edx; dwFlags
0x140051d36  mov     rcx, rax; hHeap
0x140051d39  call    cs:__imp_HeapFree
0x140051d3f  mov     rdi, [rbp+var_38]
0x140051d43  test    rdi, rdi
0x140051d46  jz      short loc_140051D5C
0x140051d48  call    cs:__imp_GetProcessHeap
0x140051d4e  mov     r8, rdi; lpMem
0x140051d51  xor     edx, edx; dwFlags
0x140051d53  mov     rcx, rax; hHeap
0x140051d56  call    cs:__imp_HeapFree
0x140051d5c  mov     eax, ebx
0x140051d5e  mov     rcx, [rbp+var_10]
0x140051d62  xor     rcx, rsp; StackCookie
0x140051d65  call    __security_check_cookie
0x140051d6a  lea     r11, [rsp+60h+var_s0]
0x140051d6f  mov     rbx, [r11+18h]
0x140051d73  mov     rdi, [r11+20h]
0x140051d77  mov     rsp, r11
0x140051d7a  pop     rbp
0x140051d7b  retn
```
