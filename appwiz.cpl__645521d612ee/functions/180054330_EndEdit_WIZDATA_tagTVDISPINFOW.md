# EndEdit(_WIZDATA *,tagTVDISPINFOW *)

- ea: `0x180054330`
- end: `0x180054421`
- name: `?EndEdit@@YAHPEAU_WIZDATA@@PEAUtagTVDISPINFOW@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(struct _WIZDATA *, struct tagTVDISPINFOW *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180054c80`

## callees

- `0x18000791c`
- `0x180054330`

## import_xrefs

- `SHELL32!__imp_PathCleanupSpec` at `0x180054396`
- `SHELL32!__imp_PathCleanupSpec` at `0x180054396`
- `SHLWAPI!PathCombineW` at `0x1800543a6`
- `SHLWAPI!PathCombineW` at `0x1800543a6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180054389`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180054389`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054410`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054410`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054353`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054353`
- `KERNEL32!MoveFileW` at `0x1800543bc`
- `KERNEL32!MoveFileW` at `0x1800543bc`
- `USER32!SendMessageW` at `0x1800543fe`
- `USER32!SendMessageW` at `0x1800543fe`

## pseudocode

```c
__int64 __fastcall EndEdit(struct _WIZDATA *a1, struct tagTVDISPINFOW *a2)
{
  unsigned int v2; // esi
  unsigned __int16 *v4; // rdi
  HWND hwndFrom; // rcx
  LPARAM lParam[2]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v8; // [rsp+30h] [rbp-58h]
  __int128 v9; // [rsp+40h] [rbp-48h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-38h]

  *((_DWORD *)a1 + 2) &= ~0x40u;
  v2 = 0;
  if ( a2->item.pszText )
  {
    v4 = (unsigned __int16 *)LocalAlloc(0, 0x20Cu);
    if ( v4 )
    {
      *(_DWORD *)v4 = *(_DWORD *)a2->item.lParam;
      StringCchCopyW(v4 + 2, 0x104u, (const unsigned __int16 *)(a2->item.lParam + 4));
      PathRemoveFileSpecW(v4 + 2);
      PathCleanupSpec(v4 + 2, a2->item.pszText);
      if ( PathCombineW(v4 + 2, v4 + 2, a2->item.pszText) && MoveFileW((LPCWSTR)(a2->item.lParam + 4), v4 + 2) )
      {
        hwndFrom = a2->hdr.hwndFrom;
        lParam[1] = (LPARAM)a2->item.hItem;
        lParam[0] = 4;
        v8 = 0;
        v10 = v4;
        v9 = 0;
        SendMessageW(hwndFrom, 0x113Fu, 0, (LPARAM)lParam);
        v4 = (unsigned __int16 *)a2->item.lParam;
        v2 = 1;
      }
      LocalFree(v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180054330  push    rbx
0x180054332  push    rbp
0x180054333  push    rsi
0x180054334  push    rdi
0x180054335  sub     rsp, 68h
0x180054339  and     dword ptr [rcx+8], 0FFFFFFBFh
0x18005433d  xor     esi, esi
0x18005433f  mov     rbx, rdx
0x180054342  cmp     [rdx+30h], rsi
0x180054346  jz      loc_180054416
0x18005434c  mov     edx, 20Ch; uBytes
0x180054351  xor     ecx, ecx; uFlags
0x180054353  call    cs:__imp_LocalAlloc
0x180054359  mov     rdi, rax
0x18005435c  test    rax, rax
0x18005435f  jz      loc_180054416
0x180054365  mov     rax, [rbx+48h]
0x180054369  lea     rbp, [rdi+4]
0x18005436d  mov     edx, 104h; unsigned __int64
0x180054372  mov     ecx, [rax]
0x180054374  mov     [rdi], ecx
0x180054376  mov     rcx, rbp; unsigned __int16 *
0x180054379  mov     r8, [rbx+48h]
0x18005437d  add     r8, 4; unsigned __int16 *
0x180054381  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054386  mov     rcx, rbp; pszPath
0x180054389  call    cs:__imp_PathRemoveFileSpecW
0x18005438f  mov     rdx, [rbx+30h]; pszSpec
0x180054393  mov     rcx, rbp; pszDir
0x180054396  call    cs:__imp_PathCleanupSpec
0x18005439c  mov     r8, [rbx+30h]; pszFile
0x1800543a0  mov     rdx, rbp; pszDir
0x1800543a3  mov     rcx, rbp; pszDest
0x1800543a6  call    cs:__imp_PathCombineW
0x1800543ac  test    rax, rax
0x1800543af  jz      short loc_18005440D
0x1800543b1  mov     rcx, [rbx+48h]
0x1800543b5  mov     rdx, rbp; lpNewFileName
0x1800543b8  add     rcx, 4; lpExistingFileName
0x1800543bc  call    cs:__imp_MoveFileW
0x1800543c2  test    eax, eax
0x1800543c4  jz      short loc_18005440D
0x1800543c6  mov     rax, [rbx+20h]
0x1800543ca  lea     r9, [rsp+88h+lParam]; lParam
0x1800543cf  mov     rcx, [rbx]; hWnd
0x1800543d2  xorps   xmm0, xmm0
0x1800543d5  movups  xmmword ptr [rsp+88h+lParam], xmm0
0x1800543da  xor     r8d, r8d; wParam
0x1800543dd  mov     [rsp+88h+lParam+8], rax
0x1800543e2  mov     edx, 113Fh; Msg
0x1800543e7  mov     dword ptr [rsp+88h+lParam], 4
0x1800543ef  movups  [rsp+88h+var_58], xmm0
0x1800543f4  mov     [rsp+88h+var_38], rdi
0x1800543f9  movups  [rsp+88h+var_48], xmm0
0x1800543fe  call    cs:__imp_SendMessageW
0x180054404  mov     rdi, [rbx+48h]
0x180054408  mov     esi, 1
0x18005440d  mov     rcx, rdi; hMem
0x180054410  call    cs:__imp_LocalFree
0x180054416  mov     eax, esi
0x180054418  add     rsp, 68h
0x18005441c  pop     rdi
0x18005441d  pop     rsi
0x18005441e  pop     rbp
0x18005441f  pop     rbx
0x180054420  retn
```
