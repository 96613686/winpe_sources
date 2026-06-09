# ImpersonateForCertAccess(ushort const *)

- ea: `0x140012d20`
- end: `0x140012e6e`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400126d4`

## callees

- `0x1400029c0`
- `0x140012d20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012e04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012e2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012e04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012e2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012e18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012e41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012e18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012e41`
- `DMCmnUtils!InvStrCmpIW` at `0x140012dab`
- `DMCmnUtils!InvStrCmpIW` at `0x140012dab`
- `DMCmnUtils!DmImpersonate` at `0x140012de2`
- `DMCmnUtils!DmImpersonate` at `0x140012de2`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140012dcc`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140012dcc`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x140012d86`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x140012d86`
- `RPCRT4!UuidFromStringW` at `0x140012d5b`
- `RPCRT4!UuidFromStringW` at `0x140012d5b`

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
              byte_140025804 = 1;
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
0x140012d20  mov     [rsp-8+arg_8], rbx
0x140012d25  mov     [rsp-8+arg_10], rdi
0x140012d2a  push    rbp
0x140012d2b  mov     rbp, rsp
0x140012d2e  sub     rsp, 60h
0x140012d32  mov     rax, cs:__security_cookie
0x140012d39  xor     rax, rsp
0x140012d3c  mov     [rbp+var_10], rax
0x140012d40  xorps   xmm0, xmm0
0x140012d43  mov     [rbp+lpMem], 0
0x140012d4b  lea     rdx, [rbp+Uuid]; Uuid
0x140012d4f  mov     [rbp+var_38], 0
0x140012d57  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x140012d5b  call    cs:__imp_UuidFromStringW
0x140012d62  nop     dword ptr [rax+rax+00h]
0x140012d67  test    eax, eax
0x140012d69  jz      short loc_140012D75
0x140012d6b  mov     ebx, 80070057h
0x140012d70  jmp     loc_140012DFB
0x140012d75  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x140012d79  lea     rdx, [rbp+var_38]
0x140012d7d  lea     rcx, [rbp+var_30]
0x140012d81  movdqa  [rbp+var_30], xmm0
0x140012d86  call    cs:__imp_GetEnrollmentCertStore
0x140012d8d  nop     dword ptr [rax+rax+00h]
0x140012d92  mov     ebx, eax
0x140012d94  test    eax, eax
0x140012d96  js      short loc_140012DFB
0x140012d98  mov     rdi, [rbp+var_38]
0x140012d9c  test    rdi, rdi
0x140012d9f  jz      short loc_140012DFB
0x140012da1  lea     rdx, aUser; "User"
0x140012da8  mov     rcx, rdi
0x140012dab  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x140012db2  nop     dword ptr [rax+rax+00h]
0x140012db7  test    eax, eax
0x140012db9  jnz     short loc_140012DFB
0x140012dbb  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x140012dbf  lea     rdx, [rbp+lpMem]
0x140012dc3  lea     rcx, [rbp+var_30]
0x140012dc7  movdqa  [rbp+var_30], xmm0
0x140012dcc  call    cs:__imp_GetEnrollmentSID
0x140012dd3  nop     dword ptr [rax+rax+00h]
0x140012dd8  mov     ebx, eax
0x140012dda  test    eax, eax
0x140012ddc  js      short loc_140012DFB
0x140012dde  mov     rcx, [rbp+lpMem]
0x140012de2  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x140012de9  nop     dword ptr [rax+rax+00h]
0x140012dee  mov     ebx, eax
0x140012df0  test    eax, eax
0x140012df2  js      short loc_140012DFB
0x140012df4  mov     cs:byte_140025804, 1
0x140012dfb  mov     rdi, [rbp+lpMem]
0x140012dff  test    rdi, rdi
0x140012e02  jz      short loc_140012E24
0x140012e04  call    cs:__imp_GetProcessHeap
0x140012e0b  nop     dword ptr [rax+rax+00h]
0x140012e10  mov     r8, rdi; lpMem
0x140012e13  xor     edx, edx; dwFlags
0x140012e15  mov     rcx, rax; hHeap
0x140012e18  call    cs:__imp_HeapFree
0x140012e1f  nop     dword ptr [rax+rax+00h]
0x140012e24  mov     rdi, [rbp+var_38]
0x140012e28  test    rdi, rdi
0x140012e2b  jz      short loc_140012E4D
0x140012e2d  call    cs:__imp_GetProcessHeap
0x140012e34  nop     dword ptr [rax+rax+00h]
0x140012e39  mov     r8, rdi; lpMem
0x140012e3c  xor     edx, edx; dwFlags
0x140012e3e  mov     rcx, rax; hHeap
0x140012e41  call    cs:__imp_HeapFree
0x140012e48  nop     dword ptr [rax+rax+00h]
0x140012e4d  mov     eax, ebx
0x140012e4f  mov     rcx, [rbp+var_10]
0x140012e53  xor     rcx, rsp; StackCookie
0x140012e56  call    __security_check_cookie
0x140012e5b  lea     r11, [rsp+60h+var_s0]
0x140012e60  mov     rbx, [r11+18h]
0x140012e64  mov     rdi, [r11+20h]
0x140012e68  mov     rsp, r11
0x140012e6b  pop     rbp
0x140012e6c  retn
```
