# UserDirPrompt(ushort const *,ushort const *,ushort *,ulong,ulong)

- ea: `0x18000b0d0`
- end: `0x18000b15f`
- name: `?UserDirPrompt@@YAHPEBG0PEAGKK@Z`
- size: `143`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063c4`

## callees

- `0x18000b0d0`
- `0x180017ff0`

## import_xrefs

- `USER32!DialogBoxParamW` at `0x18000b131`
- `USER32!DialogBoxParamW` at `0x18000b131`
- `USER32!GetSystemMetrics` at `0x18000b0fb`
- `USER32!GetSystemMetrics` at `0x18000b0fb`
- `GDI32!DeleteObject` at `0x18000b146`
- `GDI32!DeleteObject` at `0x18000b146`

## pseudocode

```c
__int64 __fastcall UserDirPrompt(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v5; // ebx
  LPARAM dwInitParam[3]; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+48h] [rbp-10h]
  unsigned int v9; // [rsp+4Ch] [rbp-Ch]

  dwInitParam[0] = (LPARAM)a1;
  dwInitParam[1] = (LPARAM)a2;
  dwInitParam[2] = (LPARAM)a3;
  v8 = 262;
  v9 = a5;
  if ( GetSystemMetrics(42) )
    g_hFont = GetSystemFont();
  v5 = DialogBoxParamW(g_hinstMUI, (LPCWSTR)0x7D0, 0, DirDlgProc, (LPARAM)dwInitParam);
  if ( g_hFont )
  {
    DeleteObject((HGDIOBJ)g_hFont);
    g_hFont = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18000b0d0  mov     rax, rsp
0x18000b0d3  push    rbx
0x18000b0d4  sub     rsp, 50h
0x18000b0d8  mov     [rax-28h], rcx
0x18000b0dc  mov     ecx, 2Ah ; '*'; nIndex
0x18000b0e1  mov     [rax-20h], rdx
0x18000b0e5  mov     [rax-18h], r8
0x18000b0e9  mov     dword ptr [rax-10h], 106h
0x18000b0f0  mov     eax, [rsp+58h+arg_20]
0x18000b0f7  mov     [rsp+58h+var_C], eax
0x18000b0fb  call    cs:__imp_GetSystemMetrics
0x18000b101  test    eax, eax
0x18000b103  jz      short loc_18000B111
0x18000b105  call    GetSystemFont
0x18000b10a  mov     cs:?g_hFont@@3PEAUHFONT__@@EA, rax; HFONT__ * g_hFont
0x18000b111  mov     rcx, cs:g_hinstMUI; hInstance
0x18000b118  lea     rax, [rsp+58h+var_28]
0x18000b11d  lea     r9, ?DirDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000b124  mov     [rsp+58h+dwInitParam], rax; dwInitParam
0x18000b129  xor     r8d, r8d; hWndParent
0x18000b12c  mov     edx, 7D0h; lpTemplateName
0x18000b131  call    cs:__imp_DialogBoxParamW
0x18000b137  mov     rcx, cs:?g_hFont@@3PEAUHFONT__@@EA; ho
0x18000b13e  mov     rbx, rax
0x18000b141  test    rcx, rcx
0x18000b144  jz      short loc_18000B157
0x18000b146  call    cs:__imp_DeleteObject
0x18000b14c  mov     cs:?g_hFont@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hFont
0x18000b157  mov     eax, ebx
0x18000b159  add     rsp, 50h
0x18000b15d  pop     rbx
0x18000b15e  retn
```
