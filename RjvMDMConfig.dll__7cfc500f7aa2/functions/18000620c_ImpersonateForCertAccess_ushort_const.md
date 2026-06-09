# ImpersonateForCertAccess(ushort const *)

- ea: `0x18000620c`
- end: `0x18000633a`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180005bfc`

## callees

- `0x180001c60`
- `0x18000620c`
- `0x180012a58`
- `0x180016b7c`
- `0x180018284`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006314`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062ff`
- `RPCRT4!UuidFromStringW` at `0x180006242`
- `RPCRT4!UuidFromStringW` at `0x180006242`

## pseudocode

```c
__int64 __fastcall ImpersonateForCertAccess(unsigned __int16 *a1)
{
  int EnrollmentString; // ebx
  const unsigned __int16 *v2; // rdx
  HANDLE ProcessHeap; // rax
  HANDLE v4; // rax
  PCNZWCH lpString1; // [rsp+20h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-38h] BYREF
  struct _GUID v8; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  lpMem = 0;
  lpString1 = 0;
  Uuid = 0;
  if ( UuidFromStringW(a1, &Uuid) )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v8 = Uuid;
    EnrollmentString = EEDBManager::GetEnrollmentString(&v8, L"SslCertStore", (unsigned __int16 **)&lpString1);
    if ( EnrollmentString >= 0 )
    {
      if ( !lpString1 )
        return (unsigned int)EnrollmentString;
      if ( !(unsigned int)InvStrCmpIW(lpString1, v2) )
      {
        v8 = Uuid;
        EnrollmentString = EEDBManager::GetEnrollmentString(&v8, L"SID", (unsigned __int16 **)&lpMem);
        if ( EnrollmentString >= 0 )
        {
          EnrollmentString = DmImpersonate((const unsigned __int16 *)lpMem);
          if ( EnrollmentString >= 0 )
            byte_180029A38 = 1;
        }
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, lpMem);
        }
      }
    }
    if ( lpString1 )
    {
      v4 = GetProcessHeap();
      HeapFree(v4, 0, (LPVOID)lpString1);
    }
  }
  return (unsigned int)EnrollmentString;
}

```

## disassembly

```asm
0x18000620c  mov     [rsp-8+arg_8], rbx
0x180006211  push    rbp
0x180006212  mov     rbp, rsp
0x180006215  sub     rsp, 60h
0x180006219  mov     rax, cs:__security_cookie
0x180006220  xor     rax, rsp
0x180006223  mov     [rbp+var_10], rax
0x180006227  xorps   xmm0, xmm0
0x18000622a  mov     [rbp+lpMem], 0
0x180006232  lea     rdx, [rbp+Uuid]; Uuid
0x180006236  mov     [rbp+lpString1], 0
0x18000623e  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180006242  call    cs:__imp_UuidFromStringW
0x180006249  nop     dword ptr [rax+rax+00h]
0x18000624e  test    eax, eax
0x180006250  jz      short loc_18000625C
0x180006252  mov     ebx, 80070057h
0x180006257  jmp     loc_180006320
0x18000625c  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180006260  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x180006264  lea     rdx, aSslcertstore; "SslCertStore"
0x18000626b  movdqa  xmmword ptr [rbp+var_30.Data1], xmm0
0x180006270  lea     rcx, [rbp+var_30]; struct _GUID
0x180006274  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180006279  mov     ebx, eax
0x18000627b  test    eax, eax
0x18000627d  js      short loc_1800062F8
0x18000627f  cmp     [rbp+lpString1], 0
0x180006284  jz      loc_180006320
0x18000628a  mov     rcx, [rbp+lpString1]; lpString1
0x18000628e  call    ?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180006293  test    eax, eax
0x180006295  jnz     short loc_1800062F8
0x180006297  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x18000629b  lea     r8, [rbp+lpMem]; unsigned __int16 **
0x18000629f  lea     rdx, aSid; "SID"
0x1800062a6  movdqa  xmmword ptr [rbp+var_30.Data1], xmm0
0x1800062ab  lea     rcx, [rbp+var_30]; struct _GUID
0x1800062af  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800062b4  mov     ebx, eax
0x1800062b6  test    eax, eax
0x1800062b8  js      short loc_1800062D0
0x1800062ba  mov     rcx, [rbp+lpMem]; unsigned __int16 *
0x1800062be  call    ?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1800062c3  mov     ebx, eax
0x1800062c5  test    eax, eax
0x1800062c7  js      short loc_1800062D0
0x1800062c9  mov     cs:byte_180029A38, 1
0x1800062d0  cmp     [rbp+lpMem], 0
0x1800062d5  jz      short loc_1800062F8
0x1800062d7  call    cs:__imp_GetProcessHeap
0x1800062de  nop     dword ptr [rax+rax+00h]
0x1800062e3  mov     r8, [rbp+lpMem]; lpMem
0x1800062e7  xor     edx, edx; dwFlags
0x1800062e9  mov     rcx, rax; hHeap
0x1800062ec  call    cs:__imp_HeapFree
0x1800062f3  nop     dword ptr [rax+rax+00h]
0x1800062f8  cmp     [rbp+lpString1], 0
0x1800062fd  jz      short loc_180006320
0x1800062ff  call    cs:__imp_GetProcessHeap
0x180006306  nop     dword ptr [rax+rax+00h]
0x18000630b  mov     r8, [rbp+lpString1]; lpMem
0x18000630f  xor     edx, edx; dwFlags
0x180006311  mov     rcx, rax; hHeap
0x180006314  call    cs:__imp_HeapFree
0x18000631b  nop     dword ptr [rax+rax+00h]
0x180006320  mov     eax, ebx
0x180006322  mov     rcx, [rbp+var_10]
0x180006326  xor     rcx, rsp; StackCookie
0x180006329  call    __security_check_cookie
0x18000632e  mov     rbx, [rsp+60h+arg_8]
0x180006333  add     rsp, 60h
0x180006337  pop     rbp
0x180006338  retn
```
