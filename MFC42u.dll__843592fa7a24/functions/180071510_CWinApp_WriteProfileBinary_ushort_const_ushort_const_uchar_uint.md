# CWinApp::WriteProfileBinary(ushort const *,ushort const *,uchar *,uint)

- ea: `0x180071510`
- end: `0x180071620`
- name: `?WriteProfileBinary@CWinApp@@QEAAHPEBG0PEAEI@Z`
- size: `272`
- prototype: `__int64 __fastcall(CWinApp *__hidden this, const unsigned __int16 *, const unsigned __int16 *, BYTE *lpData, DWORD)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000ce50`
- `0x180021160`
- `0x180021460`
- `0x180071510`

## import_xrefs

- `msvcrt!free` at `0x18007160b`
- `msvcrt!free` at `0x18007160b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180071563`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180071563`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007156e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007156e`

## pseudocode

```c
HKEY __fastcall CWinApp::WriteProfileBinary(
        CWinApp *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY result; // rax
  HKEY v10; // rdi
  LSTATUS v11; // ebx
  BYTE *v12; // rax
  __int64 v13; // r10
  BYTE *i; // rdi
  __int64 v15; // r9
  BYTE v16; // al
  unsigned int v17; // ebx

  if ( *((_QWORD *)this + 30) )
  {
    result = CWinApp::GetSectionKey(this, a2);
    v10 = result;
    if ( result )
    {
      v11 = RegSetValueExW(result, a3, 0, 3u, lpData, cbData);
      RegCloseKey(v10);
      return (HKEY)(v11 == 0);
    }
  }
  else
  {
    v12 = (BYTE *)operator new(saturated_mul(2 * cbData + 1, 2u));
    v13 = 0;
    for ( i = v12; (unsigned int)v13 < cbData; *(_WORD *)&i[2 * (unsigned int)(v15 + 1)] = (v16 >> 4) + 65 )
    {
      v15 = (unsigned int)(2 * v13);
      *(_WORD *)&i[2 * v15] = (lpData[v13] & 0xF) + 65;
      v16 = lpData[v13];
      v13 = (unsigned int)(v13 + 1);
    }
    *(_WORD *)&i[2 * (unsigned int)(2 * v13)] = 0;
    v17 = CWinApp::WriteProfileStringW((LPCWSTR *)this, a2, a3, i);
    free(i);
    return (HKEY)v17;
  }
  return result;
}

```

## disassembly

```asm
0x180071510  push    rbx
0x180071512  push    rbp
0x180071513  push    rsi
0x180071514  push    rdi
0x180071515  push    r14
0x180071517  push    r15
0x180071519  sub     rsp, 38h
0x18007151d  cmp     qword ptr [rcx+0F0h], 0
0x180071525  mov     rbp, r9
0x180071528  mov     r14, r8
0x18007152b  mov     rsi, rdx
0x18007152e  mov     rbx, rcx
0x180071531  jz      short loc_180071580
0x180071533  call    ?GetSectionKey@CWinApp@@QEAAPEAUHKEY__@@PEBG@Z; CWinApp::GetSectionKey(ushort const *)
0x180071538  mov     rdi, rax
0x18007153b  test    rax, rax
0x18007153e  jz      loc_180071613
0x180071544  mov     eax, [rsp+68h+arg_20]
0x18007154b  mov     r9d, 3; dwType
0x180071551  mov     [rsp+68h+cbData], eax; cbData
0x180071555  xor     r8d, r8d; Reserved
0x180071558  mov     rdx, r14; lpValueName
0x18007155b  mov     [rsp+68h+lpData], rbp; lpData
0x180071560  mov     rcx, rdi; hKey
0x180071563  call    cs:__imp_RegSetValueExW
0x180071569  mov     rcx, rdi; hKey
0x18007156c  mov     ebx, eax
0x18007156e  call    cs:__imp_RegCloseKey
0x180071574  xor     eax, eax
0x180071576  test    ebx, ebx
0x180071578  setz    al
0x18007157b  jmp     loc_180071613
0x180071580  mov     r15d, [rsp+68h+arg_20]
0x180071588  mov     eax, 2
0x18007158d  lea     ecx, ds:1[r15*2]
0x180071595  mul     rcx
0x180071598  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007159f  cmovb   rax, rcx
0x1800715a3  mov     rcx, rax; Size
0x1800715a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800715ab  xor     r10d, r10d
0x1800715ae  mov     rdi, rax
0x1800715b1  test    r15d, r15d
0x1800715b4  jz      short loc_1800715EB
0x1800715b6  mov     cl, [r10+rbp]
0x1800715ba  lea     r9d, [r10+r10]
0x1800715be  and     cl, 0Fh
0x1800715c1  movzx   edx, cl
0x1800715c4  add     dx, 41h ; 'A'
0x1800715c8  mov     [rdi+r9*2], dx
0x1800715cd  mov     al, [r10+rbp]
0x1800715d1  inc     r10d
0x1800715d4  shr     al, 4
0x1800715d7  movzx   edx, al
0x1800715da  lea     eax, [r9+1]
0x1800715de  add     dx, 41h ; 'A'
0x1800715e2  mov     [rdi+rax*2], dx
0x1800715e6  cmp     r10d, r15d
0x1800715e9  jb      short loc_1800715B6
0x1800715eb  lea     ecx, [r10+r10]
0x1800715ef  xor     eax, eax
0x1800715f1  mov     [rdi+rcx*2], ax
0x1800715f5  mov     r9, rdi; unsigned __int16 *
0x1800715f8  mov     rcx, rbx; this
0x1800715fb  mov     r8, r14; unsigned __int16 *
0x1800715fe  mov     rdx, rsi; unsigned __int16 *
0x180071601  call    ?WriteProfileStringW@CWinApp@@QEAAHPEBG00@Z; CWinApp::WriteProfileStringW(ushort const *,ushort const *,ushort const *)
0x180071606  mov     rcx, rdi; Block
0x180071609  mov     ebx, eax
0x18007160b  call    cs:__imp_free
0x180071611  mov     eax, ebx
0x180071613  add     rsp, 38h
0x180071617  pop     r15
0x180071619  pop     r14
0x18007161b  pop     rdi
0x18007161c  pop     rsi
0x18007161d  pop     rbp
0x18007161e  pop     rbx
0x18007161f  retn
```
