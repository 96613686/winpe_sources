# ImpersonateForCertAccess(ushort const *)

- ea: `0x180095bb8`
- end: `0x180095d06`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800954f0`

## callees

- `0x180004eb0`
- `0x180095bb8`

## import_xrefs

- `DMCmnUtils!DmImpersonate` at `0x180095c7a`
- `DMCmnUtils!DmImpersonate` at `0x180095c7a`
- `DMCmnUtils!InvStrCmpIW` at `0x180095c43`
- `DMCmnUtils!InvStrCmpIW` at `0x180095c43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095c9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095cc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095c9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095cc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095cb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095cd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095cb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095cd9`
- `RPCRT4!UuidFromStringW` at `0x180095bf3`
- `RPCRT4!UuidFromStringW` at `0x180095bf3`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x180095c1e`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x180095c1e`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180095c64`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180095c64`

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
              byte_1800FF444 = 1;
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
0x180095bb8  mov     [rsp-8+arg_8], rbx
0x180095bbd  mov     [rsp-8+arg_10], rdi
0x180095bc2  push    rbp
0x180095bc3  mov     rbp, rsp
0x180095bc6  sub     rsp, 60h
0x180095bca  mov     rax, cs:__security_cookie
0x180095bd1  xor     rax, rsp
0x180095bd4  mov     [rbp+var_10], rax
0x180095bd8  xorps   xmm0, xmm0
0x180095bdb  mov     [rbp+lpMem], 0
0x180095be3  lea     rdx, [rbp+Uuid]; Uuid
0x180095be7  mov     [rbp+var_38], 0
0x180095bef  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180095bf3  call    cs:__imp_UuidFromStringW
0x180095bfa  nop     dword ptr [rax+rax+00h]
0x180095bff  test    eax, eax
0x180095c01  jz      short loc_180095C0D
0x180095c03  mov     ebx, 80070057h
0x180095c08  jmp     loc_180095C93
0x180095c0d  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180095c11  lea     rdx, [rbp+var_38]
0x180095c15  lea     rcx, [rbp+var_30]
0x180095c19  movdqa  [rbp+var_30], xmm0
0x180095c1e  call    cs:__imp_GetEnrollmentCertStore
0x180095c25  nop     dword ptr [rax+rax+00h]
0x180095c2a  mov     ebx, eax
0x180095c2c  test    eax, eax
0x180095c2e  js      short loc_180095C93
0x180095c30  mov     rdi, [rbp+var_38]
0x180095c34  test    rdi, rdi
0x180095c37  jz      short loc_180095C93
0x180095c39  lea     rdx, aUser_0; "User"
0x180095c40  mov     rcx, rdi
0x180095c43  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180095c4a  nop     dword ptr [rax+rax+00h]
0x180095c4f  test    eax, eax
0x180095c51  jnz     short loc_180095C93
0x180095c53  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180095c57  lea     rdx, [rbp+lpMem]
0x180095c5b  lea     rcx, [rbp+var_30]
0x180095c5f  movdqa  [rbp+var_30], xmm0
0x180095c64  call    cs:__imp_GetEnrollmentSID
0x180095c6b  nop     dword ptr [rax+rax+00h]
0x180095c70  mov     ebx, eax
0x180095c72  test    eax, eax
0x180095c74  js      short loc_180095C93
0x180095c76  mov     rcx, [rbp+lpMem]
0x180095c7a  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180095c81  nop     dword ptr [rax+rax+00h]
0x180095c86  mov     ebx, eax
0x180095c88  test    eax, eax
0x180095c8a  js      short loc_180095C93
0x180095c8c  mov     cs:byte_1800FF444, 1
0x180095c93  mov     rdi, [rbp+lpMem]
0x180095c97  test    rdi, rdi
0x180095c9a  jz      short loc_180095CBC
0x180095c9c  call    cs:__imp_GetProcessHeap
0x180095ca3  nop     dword ptr [rax+rax+00h]
0x180095ca8  mov     r8, rdi; lpMem
0x180095cab  xor     edx, edx; dwFlags
0x180095cad  mov     rcx, rax; hHeap
0x180095cb0  call    cs:__imp_HeapFree
0x180095cb7  nop     dword ptr [rax+rax+00h]
0x180095cbc  mov     rdi, [rbp+var_38]
0x180095cc0  test    rdi, rdi
0x180095cc3  jz      short loc_180095CE5
0x180095cc5  call    cs:__imp_GetProcessHeap
0x180095ccc  nop     dword ptr [rax+rax+00h]
0x180095cd1  mov     r8, rdi; lpMem
0x180095cd4  xor     edx, edx; dwFlags
0x180095cd6  mov     rcx, rax; hHeap
0x180095cd9  call    cs:__imp_HeapFree
0x180095ce0  nop     dword ptr [rax+rax+00h]
0x180095ce5  mov     eax, ebx
0x180095ce7  mov     rcx, [rbp+var_10]
0x180095ceb  xor     rcx, rsp; StackCookie
0x180095cee  call    __security_check_cookie
0x180095cf3  lea     r11, [rsp+60h+var_s0]
0x180095cf8  mov     rbx, [r11+18h]
0x180095cfc  mov     rdi, [r11+20h]
0x180095d00  mov     rsp, r11
0x180095d03  pop     rbp
0x180095d04  retn
```
