# ImpersonateForCertAccess(ushort const *)

- ea: `0x140012458`
- end: `0x14001256c`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140011eb4`

## callees

- `0x140002930`
- `0x140012458`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001251b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001251b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012529`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012546`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012529`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012546`
- `DMCmnUtils!InvStrCmpIW` at `0x1400124d4`
- `DMCmnUtils!InvStrCmpIW` at `0x1400124d4`
- `DMCmnUtils!DmImpersonate` at `0x1400124ff`
- `DMCmnUtils!DmImpersonate` at `0x1400124ff`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1400124ef`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1400124ef`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1400124b5`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1400124b5`
- `RPCRT4!UuidFromStringW` at `0x140012493`
- `RPCRT4!UuidFromStringW` at `0x140012493`

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
              byte_140024704 = 1;
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
0x140012458  mov     [rsp-8+arg_8], rbx
0x14001245d  mov     [rsp-8+arg_10], rdi
0x140012462  push    rbp
0x140012463  mov     rbp, rsp
0x140012466  sub     rsp, 60h
0x14001246a  mov     rax, cs:__security_cookie
0x140012471  xor     rax, rsp
0x140012474  mov     [rbp+var_10], rax
0x140012478  xorps   xmm0, xmm0
0x14001247b  mov     [rbp+lpMem], 0
0x140012483  lea     rdx, [rbp+Uuid]; Uuid
0x140012487  mov     [rbp+var_38], 0
0x14001248f  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x140012493  call    cs:__imp_UuidFromStringW
0x140012499  test    eax, eax
0x14001249b  jz      short loc_1400124A4
0x14001249d  mov     ebx, 80070057h
0x1400124a2  jmp     short loc_140012512
0x1400124a4  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1400124a8  lea     rdx, [rbp+var_38]
0x1400124ac  lea     rcx, [rbp+var_30]
0x1400124b0  movdqa  [rbp+var_30], xmm0
0x1400124b5  call    cs:__imp_GetEnrollmentCertStore
0x1400124bb  mov     ebx, eax
0x1400124bd  test    eax, eax
0x1400124bf  js      short loc_140012512
0x1400124c1  mov     rdi, [rbp+var_38]
0x1400124c5  test    rdi, rdi
0x1400124c8  jz      short loc_140012512
0x1400124ca  lea     rdx, aUser; "User"
0x1400124d1  mov     rcx, rdi
0x1400124d4  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x1400124da  test    eax, eax
0x1400124dc  jnz     short loc_140012512
0x1400124de  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1400124e2  lea     rdx, [rbp+lpMem]
0x1400124e6  lea     rcx, [rbp+var_30]
0x1400124ea  movdqa  [rbp+var_30], xmm0
0x1400124ef  call    cs:__imp_GetEnrollmentSID
0x1400124f5  mov     ebx, eax
0x1400124f7  test    eax, eax
0x1400124f9  js      short loc_140012512
0x1400124fb  mov     rcx, [rbp+lpMem]
0x1400124ff  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x140012505  mov     ebx, eax
0x140012507  test    eax, eax
0x140012509  js      short loc_140012512
0x14001250b  mov     cs:byte_140024704, 1
0x140012512  mov     rdi, [rbp+lpMem]
0x140012516  test    rdi, rdi
0x140012519  jz      short loc_14001252F
0x14001251b  call    cs:__imp_GetProcessHeap
0x140012521  mov     r8, rdi; lpMem
0x140012524  xor     edx, edx; dwFlags
0x140012526  mov     rcx, rax; hHeap
0x140012529  call    cs:__imp_HeapFree
0x14001252f  mov     rdi, [rbp+var_38]
0x140012533  test    rdi, rdi
0x140012536  jz      short loc_14001254C
0x140012538  call    cs:__imp_GetProcessHeap
0x14001253e  mov     r8, rdi; lpMem
0x140012541  xor     edx, edx; dwFlags
0x140012543  mov     rcx, rax; hHeap
0x140012546  call    cs:__imp_HeapFree
0x14001254c  mov     eax, ebx
0x14001254e  mov     rcx, [rbp+var_10]
0x140012552  xor     rcx, rsp; StackCookie
0x140012555  call    __security_check_cookie
0x14001255a  lea     r11, [rsp+60h+var_s0]
0x14001255f  mov     rbx, [r11+18h]
0x140012563  mov     rdi, [r11+20h]
0x140012567  mov     rsp, r11
0x14001256a  pop     rbp
0x14001256b  retn
```
