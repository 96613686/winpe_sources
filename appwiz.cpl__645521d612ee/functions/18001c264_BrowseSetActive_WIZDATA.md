# BrowseSetActive(_WIZDATA *)

- ea: `0x18001c264`
- end: `0x18001c308`
- name: `?BrowseSetActive@@YAXPEAU_WIZDATA@@@Z`
- size: `164`
- prototype: `void __fastcall(struct _WIZDATA *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c118`
- `0x18001c5cc`
- `0x18001ce3c`
- `0x18001d0a0`

## callees

- `0x180007828`
- `0x18000791c`
- `0x18001c264`
- `0x18001cde0`

## import_xrefs

- `SHLWAPI!PathQuoteSpacesW` at `0x18001c28f`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001c28f`
- `USER32!GetDlgItem` at `0x18001c2cb`
- `USER32!GetDlgItem` at `0x18001c2cb`
- `USER32!SetWindowTextW` at `0x18001c2d7`
- `USER32!SetWindowTextW` at `0x18001c2d7`
- `USER32!PostMessageW` at `0x18001c2f3`
- `USER32!PostMessageW` at `0x18001c2f3`

## pseudocode

```c
void __fastcall BrowseSetActive(struct _WIZDATA *a1)
{
  WCHAR *v1; // rbx
  HWND DlgItem; // rax

  v1 = (WCHAR *)((char *)a1 + 1572);
  StringCchCopyW((unsigned __int16 *)a1 + 786, 0x104u, (const unsigned __int16 *)a1 + 6);
  PathQuoteSpacesW(v1);
  if ( *((_WORD *)a1 + 526) )
  {
    StringCchCatW(v1, 0x104u, L" ");
    StringCchCatW(v1, 0x104u, (const unsigned __int16 *)a1 + 526);
  }
  DlgItem = GetDlgItem(*(HWND *)a1, 1003);
  SetWindowTextW(DlgItem, v1);
  SetBrowseButtons(a1);
  PostMessageW(*(HWND *)a1, 0x8000u, 0, 0);
  *v1 = 0;
}

```

## disassembly

```asm
0x18001c264  push    rbx
0x18001c266  push    rbp
0x18001c267  push    rsi
0x18001c268  push    rdi
0x18001c269  push    r14
0x18001c26b  sub     rsp, 20h
0x18001c26f  lea     rbx, [rcx+624h]
0x18001c276  mov     rdi, rcx
0x18001c279  lea     r8, [rcx+0Ch]; unsigned __int16 *
0x18001c27d  mov     ebp, 104h
0x18001c282  mov     edx, ebp; unsigned __int64
0x18001c284  mov     rcx, rbx; unsigned __int16 *
0x18001c287  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c28c  mov     rcx, rbx; lpsz
0x18001c28f  call    cs:__imp_PathQuoteSpacesW
0x18001c295  lea     rsi, [rdi+41Ch]
0x18001c29c  xor     r14d, r14d
0x18001c29f  cmp     [rsi], r14w
0x18001c2a3  jz      short loc_18001C2C3
0x18001c2a5  lea     r8, asc_180064CC0; " "
0x18001c2ac  mov     edx, ebp; unsigned __int64
0x18001c2ae  mov     rcx, rbx; unsigned __int16 *
0x18001c2b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c2b6  mov     r8, rsi; unsigned __int16 *
0x18001c2b9  mov     edx, ebp; unsigned __int64
0x18001c2bb  mov     rcx, rbx; unsigned __int16 *
0x18001c2be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c2c3  mov     rcx, [rdi]; hDlg
0x18001c2c6  mov     edx, 3EBh; nIDDlgItem
0x18001c2cb  call    cs:__imp_GetDlgItem
0x18001c2d1  mov     rcx, rax; hWnd
0x18001c2d4  mov     rdx, rbx; lpString
0x18001c2d7  call    cs:__imp_SetWindowTextW
0x18001c2dd  mov     rcx, rdi; struct _WIZDATA *
0x18001c2e0  call    ?SetBrowseButtons@@YAXPEAU_WIZDATA@@@Z; SetBrowseButtons(_WIZDATA *)
0x18001c2e5  mov     rcx, [rdi]; hWnd
0x18001c2e8  xor     r9d, r9d; lParam
0x18001c2eb  xor     r8d, r8d; wParam
0x18001c2ee  mov     edx, 8000h; Msg
0x18001c2f3  call    cs:__imp_PostMessageW
0x18001c2f9  mov     [rbx], r14w
0x18001c2fd  add     rsp, 20h
0x18001c301  pop     r14
0x18001c303  pop     rdi
0x18001c304  pop     rsi
0x18001c305  pop     rbp
0x18001c306  pop     rbx
0x18001c307  retn
```
