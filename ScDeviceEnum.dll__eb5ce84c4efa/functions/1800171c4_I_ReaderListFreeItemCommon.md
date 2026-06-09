# I_ReaderListFreeItemCommon

- ea: `0x1800171c4`
- end: `0x1800172fb`
- name: `I_ReaderListFreeItemCommon`
- size: `311`
- prototype: `SECURITY_STATUS __fastcall(_QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800163b8`
- `0x180017178`

## callees

- `0x180014018`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001724c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017264`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001727c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001724c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017264`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001727c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172c4`
- `CRYPT32!CertCloseStore` at `0x180017219`
- `CRYPT32!CertCloseStore` at `0x18001722d`
- `CRYPT32!CertCloseStore` at `0x180017219`
- `CRYPT32!CertCloseStore` at `0x18001722d`
- `ncrypt!NCryptFreeObject` at `0x1800172ea`
- `ncrypt!NCryptFreeObject` at `0x1800172ea`
- `CRYPTSP!CryptReleaseContext` at `0x1800172d8`
- `CRYPTSP!CryptReleaseContext` at `0x1800172d8`

## pseudocode

```c
SECURITY_STATUS __fastcall I_ReaderListFreeItemCommon(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rcx
  SECURITY_STATUS result; // eax
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // r8
  void *v9; // r8
  void *v10; // r8
  void *v11; // r8
  void *v12; // r8
  void *v13; // r8
  HCRYPTPROV v14; // rcx
  NCRYPT_HANDLE v15; // rcx

  if ( a2 )
    *a2 = 0;
  v4 = a1[29];
  while ( v4 )
  {
    a1[29] = *(_QWORD *)(v4 + 104);
    result = I_FreeCredListItem((LPVOID *)v4);
    v4 = a1[29];
    if ( a2 )
      ++*a2;
  }
  v6 = (void *)a1[21];
  if ( v6 )
    result = CertCloseStore(v6, 0);
  v7 = (void *)a1[22];
  if ( v7 )
  {
    result = CertCloseStore(v7, 0);
    if ( a2 )
      ++*a2;
  }
  v8 = (void *)a1[13];
  if ( v8 )
    result = HeapFree(hHeap, 0, v8);
  v9 = (void *)a1[14];
  if ( v9 )
    result = HeapFree(hHeap, 0, v9);
  v10 = (void *)a1[2];
  if ( v10 )
    result = HeapFree(hHeap, 0, v10);
  v11 = (void *)a1[10];
  if ( v11 )
    result = HeapFree(hHeap, 0, v11);
  v12 = (void *)a1[11];
  if ( v12 )
    result = HeapFree(hHeap, 0, v12);
  v13 = (void *)a1[12];
  if ( v13 )
    result = HeapFree(hHeap, 0, v13);
  v14 = a1[16];
  if ( v14 )
    result = CryptReleaseContext(v14, 0);
  v15 = a1[17];
  if ( v15 )
    return NCryptFreeObject(v15);
  return result;
}

```

## disassembly

```asm
0x1800171c4  mov     [rsp+arg_0], rbx
0x1800171c9  push    rdi
0x1800171ca  sub     rsp, 20h
0x1800171ce  mov     rdi, rdx
0x1800171d1  mov     rbx, rcx
0x1800171d4  test    rdx, rdx
0x1800171d7  jz      short loc_1800171DF
0x1800171d9  mov     dword ptr [rdx], 0
0x1800171df  mov     rcx, [rcx+0E8h]
0x1800171e6  jmp     short loc_180017206
0x1800171e8  mov     rax, [rcx+68h]
0x1800171ec  mov     [rbx+0E8h], rax
0x1800171f3  call    I_FreeCredListItem
0x1800171f8  mov     rcx, [rbx+0E8h]; lpMem
0x1800171ff  test    rdi, rdi
0x180017202  jz      short loc_180017206
0x180017204  inc     dword ptr [rdi]
0x180017206  test    rcx, rcx
0x180017209  jnz     short loc_1800171E8
0x18001720b  mov     rcx, [rbx+0A8h]; hCertStore
0x180017212  test    rcx, rcx
0x180017215  jz      short loc_18001721F
0x180017217  xor     edx, edx; dwFlags
0x180017219  call    cs:__imp_CertCloseStore
0x18001721f  mov     rcx, [rbx+0B0h]; hCertStore
0x180017226  test    rcx, rcx
0x180017229  jz      short loc_18001723A
0x18001722b  xor     edx, edx; dwFlags
0x18001722d  call    cs:__imp_CertCloseStore
0x180017233  test    rdi, rdi
0x180017236  jz      short loc_18001723A
0x180017238  inc     dword ptr [rdi]
0x18001723a  mov     r8, [rbx+68h]; lpMem
0x18001723e  test    r8, r8
0x180017241  jz      short loc_180017252
0x180017243  mov     rcx, cs:hHeap; hHeap
0x18001724a  xor     edx, edx; dwFlags
0x18001724c  call    cs:__imp_HeapFree
0x180017252  mov     r8, [rbx+70h]; lpMem
0x180017256  test    r8, r8
0x180017259  jz      short loc_18001726A
0x18001725b  mov     rcx, cs:hHeap; hHeap
0x180017262  xor     edx, edx; dwFlags
0x180017264  call    cs:__imp_HeapFree
0x18001726a  mov     r8, [rbx+10h]; lpMem
0x18001726e  test    r8, r8
0x180017271  jz      short loc_180017282
0x180017273  mov     rcx, cs:hHeap; hHeap
0x18001727a  xor     edx, edx; dwFlags
0x18001727c  call    cs:__imp_HeapFree
0x180017282  mov     r8, [rbx+50h]; lpMem
0x180017286  test    r8, r8
0x180017289  jz      short loc_18001729A
0x18001728b  mov     rcx, cs:hHeap; hHeap
0x180017292  xor     edx, edx; dwFlags
0x180017294  call    cs:__imp_HeapFree
0x18001729a  mov     r8, [rbx+58h]; lpMem
0x18001729e  test    r8, r8
0x1800172a1  jz      short loc_1800172B2
0x1800172a3  mov     rcx, cs:hHeap; hHeap
0x1800172aa  xor     edx, edx; dwFlags
0x1800172ac  call    cs:__imp_HeapFree
0x1800172b2  mov     r8, [rbx+60h]; lpMem
0x1800172b6  test    r8, r8
0x1800172b9  jz      short loc_1800172CA
0x1800172bb  mov     rcx, cs:hHeap; hHeap
0x1800172c2  xor     edx, edx; dwFlags
0x1800172c4  call    cs:__imp_HeapFree
0x1800172ca  mov     rcx, [rbx+80h]; hProv
0x1800172d1  test    rcx, rcx
0x1800172d4  jz      short loc_1800172DE
0x1800172d6  xor     edx, edx; dwFlags
0x1800172d8  call    cs:__imp_CryptReleaseContext
0x1800172de  mov     rcx, [rbx+88h]; hObject
0x1800172e5  test    rcx, rcx
0x1800172e8  jz      short loc_1800172F0
0x1800172ea  call    cs:__imp_NCryptFreeObject
0x1800172f0  mov     rbx, [rsp+28h+arg_0]
0x1800172f5  add     rsp, 20h
0x1800172f9  pop     rdi
0x1800172fa  retn
```
