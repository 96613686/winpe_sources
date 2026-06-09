# CShellBrowser::_QueryNewPalette(void)

- ea: `0x18004d710`
- end: `0x18004d947`
- name: `?_QueryNewPalette@CShellBrowser@@AEAAHXZ`
- size: `567`
- prototype: `__int64 __fastcall(CShellBrowser *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004d29c`
- `0x18004ec84`

## callees

- `0x18004d710`
- `0x1801d4514`
- `0x1801d50b0`
- `0x180210010`

## import_xrefs

- `SHLWAPI!SHCreateShellPalette` at `0x18004d867`
- `SHLWAPI!SHCreateShellPalette` at `0x18004d867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d84d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d84d`
- `USER32!GetDC` at `0x18004d899`
- `USER32!GetDC` at `0x18004d899`
- `USER32!SendMessageW` at `0x18004d785`
- `USER32!SendMessageW` at `0x18004d785`
- `USER32!ReleaseDC` at `0x18004d8c2`
- `USER32!ReleaseDC` at `0x18004d8c2`
- `GDI32!DeleteObject` at `0x18004d882`
- `GDI32!DeleteObject` at `0x18004d90c`
- `GDI32!DeleteObject` at `0x18004d882`
- `GDI32!DeleteObject` at `0x18004d90c`
- `GDI32!GetDeviceCaps` at `0x18004d8af`
- `GDI32!GetDeviceCaps` at `0x18004d8af`
- `GDI32!CreatePalette` at `0x18004d81d`
- `GDI32!CreatePalette` at `0x18004d81d`

## pseudocode

```c
__int64 __fastcall CShellBrowser::_QueryNewPalette(CShellBrowser *this)
{
  unsigned int v2; // esi
  int v3; // r15d
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  HWND v11; // rcx
  __int64 v12; // rcx
  HPALETTE Palette; // rbp
  int v14; // r14d
  int v15; // eax
  int v16; // ebx
  LOGPALETTE *v17; // rcx
  int updated; // eax
  HPALETTE v19; // rax
  HDC DC; // rax
  HDC v21; // rbp
  int v22; // ebx
  HPALETTE v23; // rcx
  LOGPALETTE *plpal; // [rsp+80h] [rbp+8h] BYREF

  v2 = 1;
  v3 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v4 = *((_DWORD *)this + 240);
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
              break;
          }
        }
        DC = GetDC(0);
        v21 = DC;
        if ( DC )
        {
          v22 = GetDeviceCaps(DC, 38) & 0x100;
          ReleaseDC(0, v21);
          *((_DWORD *)this + 240) = v22 != 0 ? 3 : 7;
          if ( v22 )
            continue;
        }
        goto LABEL_35;
      }
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
          break;
      }
      v12 = *((_QWORD *)this + 56);
      plpal = 0;
      if ( !v12 )
        goto LABEL_28;
      Palette = 0;
      v14 = 6;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD, _QWORD, LOGPALETTE **))(*(_QWORD *)v12 + 32LL))(
              v12,
              1,
              0xFFFFFFFFLL,
              0,
              0,
              0,
              &plpal);
      v16 = v15;
      if ( v15 >= 0 )
      {
        v17 = plpal;
        if ( plpal )
        {
          if ( v15 != 1 )
          {
            updated = CShellBrowser::_UpdateBrowserPaletteInPlace(this, plpal);
            if ( updated >= 0 )
            {
              Palette = (HPALETTE)*((_QWORD *)this + 121);
              if ( updated == 1 )
                v3 = 1;
            }
            else
            {
              Palette = CreatePalette(plpal);
            }
            v17 = plpal;
            if ( Palette )
              v14 = 5;
          }
        }
        else
        {
          v16 = 1;
        }
        if ( v17 )
          CoTaskMemFree(v17);
        if ( v16 == 1 )
          goto LABEL_28;
      }
LABEL_37:
      v23 = (HPALETTE)*((_QWORD *)this + 121);
      if ( Palette != v23 )
      {
        if ( v23 )
        {
          if ( v23 != g_hpalHalftone )
            DeleteObject(v23);
        }
        *((_QWORD *)this + 121) = Palette;
      }
      *((_DWORD *)this + 240) = v14;
    }
    v9 = v8 - 1;
    if ( !v9 )
      break;
    v10 = v9 - 1;
    if ( !v10 )
    {
      v11 = (HWND)*((_QWORD *)this + 53);
      if ( v11 && SendMessageW(v11, 0x30Fu, 0, 0) )
        return v2;
LABEL_28:
      if ( !g_hpalHalftone )
      {
        v19 = SHCreateShellPalette(0);
        if ( v19 )
        {
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hpalHalftone, (signed __int64)v19, 0) )
            DeleteObject(v19);
        }
      }
      Palette = (HPALETTE)g_hpalHalftone;
      v14 = 5;
      goto LABEL_37;
    }
    if ( v10 == 1 )
    {
LABEL_35:
      if ( !*((_QWORD *)this + 121) )
        return 0;
      Palette = 0;
      v14 = 7;
      goto LABEL_37;
    }
    *((_DWORD *)this + 240) = 1;
  }
  if ( !v3 )
    CShellBrowser::_RealizeBrowserPalette(this, 0);
  return v2;
}

```

## disassembly

```asm
0x18004d710  push    rbx
0x18004d712  push    rbp
0x18004d713  push    rsi
0x18004d714  push    rdi
0x18004d715  push    r14
0x18004d717  push    r15
0x18004d719  sub     rsp, 48h
0x18004d71d  mov     rdi, rcx
0x18004d720  mov     esi, 1
0x18004d725  xor     r15d, r15d
0x18004d728  mov     ecx, [rdi+3C0h]
0x18004d72e  test    ecx, ecx
0x18004d730  jz      loc_18004D897
0x18004d736  sub     ecx, esi
0x18004d738  jz      loc_18004D897
0x18004d73e  sub     ecx, esi
0x18004d740  jz      loc_18004D897
0x18004d746  sub     ecx, esi
0x18004d748  jz      short loc_18004D799
0x18004d74a  sub     ecx, esi
0x18004d74c  jz      short loc_18004D799
0x18004d74e  sub     ecx, esi
0x18004d750  jz      loc_18004D925
0x18004d756  sub     ecx, esi
0x18004d758  jz      short loc_18004D76A
0x18004d75a  cmp     ecx, esi
0x18004d75c  jz      loc_18004D8E2
0x18004d762  mov     [rdi+3C0h], esi
0x18004d768  jmp     short loc_18004D728
0x18004d76a  mov     rcx, [rdi+1A8h]; hWnd
0x18004d771  test    rcx, rcx
0x18004d774  jz      loc_18004D85B
0x18004d77a  xor     r9d, r9d; lParam
0x18004d77d  xor     r8d, r8d; wParam
0x18004d780  mov     edx, 30Fh; Msg
0x18004d785  call    cs:__imp_SendMessageW
0x18004d78b  test    rax, rax
0x18004d78e  jz      loc_18004D85B
0x18004d794  jmp     loc_18004D938
0x18004d799  mov     rcx, [rdi+1C0h]
0x18004d7a0  mov     [rsp+78h+plpal], 0
0x18004d7ac  test    rcx, rcx
0x18004d7af  jz      loc_18004D85B
0x18004d7b5  mov     rax, [rcx]
0x18004d7b8  lea     rdx, [rsp+78h+plpal]
0x18004d7c0  mov     [rsp+78h+var_48], rdx
0x18004d7c5  xor     ebp, ebp
0x18004d7c7  mov     [rsp+78h+var_50], rbp
0x18004d7cc  xor     r9d, r9d
0x18004d7cf  or      r8d, 0FFFFFFFFh
0x18004d7d3  mov     [rsp+78h+var_58], rbp
0x18004d7d8  mov     rax, [rax+20h]
0x18004d7dc  mov     edx, esi
0x18004d7de  lea     r14d, [rbp+6]
0x18004d7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7e7  mov     ebx, eax
0x18004d7e9  test    eax, eax
0x18004d7eb  js      loc_18004D8F2
0x18004d7f1  mov     rcx, [rsp+78h+plpal]
0x18004d7f9  test    rcx, rcx
0x18004d7fc  jnz     short loc_18004D802
0x18004d7fe  mov     ebx, esi
0x18004d800  jmp     short loc_18004D848
0x18004d802  cmp     eax, esi
0x18004d804  jz      short loc_18004D848
0x18004d806  mov     rdx, rcx; struct tagLOGPALETTE *
0x18004d809  mov     rcx, rdi; this
0x18004d80c  call    ?_UpdateBrowserPaletteInPlace@CShellBrowser@@AEAAJPEBUtagLOGPALETTE@@@Z; CShellBrowser::_UpdateBrowserPaletteInPlace(tagLOGPALETTE const *)
0x18004d811  test    eax, eax
0x18004d813  jns     short loc_18004D828
0x18004d815  mov     rcx, [rsp+78h+plpal]; plpal
0x18004d81d  call    cs:__imp_CreatePalette
0x18004d823  mov     rbp, rax
0x18004d826  jmp     short loc_18004D835
0x18004d828  mov     rbp, [rdi+3C8h]
0x18004d82f  cmp     eax, esi
0x18004d831  cmovz   r15d, esi
0x18004d835  mov     rcx, [rsp+78h+plpal]; pv
0x18004d83d  test    rbp, rbp
0x18004d840  jz      short loc_18004D848
0x18004d842  mov     r14d, 5
0x18004d848  test    rcx, rcx
0x18004d84b  jz      short loc_18004D853
0x18004d84d  call    cs:__imp_CoTaskMemFree
0x18004d853  cmp     ebx, esi
0x18004d855  jnz     loc_18004D8F2
0x18004d85b  cmp     cs:?g_hpalHalftone@@3PEAUHPALETTE__@@EA, 0; HPALETTE__ * g_hpalHalftone
0x18004d863  jnz     short loc_18004D888
0x18004d865  xor     ecx, ecx; hdc
0x18004d867  call    cs:__imp_SHCreateShellPalette
0x18004d86d  mov     rcx, rax; ho
0x18004d870  test    rax, rax
0x18004d873  jz      short loc_18004D888
0x18004d875  xor     eax, eax
0x18004d877  lock cmpxchg cs:?g_hpalHalftone@@3PEAUHPALETTE__@@EA, rcx; HPALETTE__ * g_hpalHalftone
0x18004d880  jz      short loc_18004D888
0x18004d882  call    cs:__imp_DeleteObject
0x18004d888  mov     rbp, cs:?g_hpalHalftone@@3PEAUHPALETTE__@@EA; HPALETTE__ * g_hpalHalftone
0x18004d88f  mov     r14d, 5
0x18004d895  jmp     short loc_18004D8F2
0x18004d897  xor     ecx, ecx; hWnd
0x18004d899  call    cs:__imp_GetDC
0x18004d89f  mov     rbp, rax
0x18004d8a2  test    rax, rax
0x18004d8a5  jz      short loc_18004D8E2
0x18004d8a7  mov     edx, 26h ; '&'; index
0x18004d8ac  mov     rcx, rax; hdc
0x18004d8af  call    cs:__imp_GetDeviceCaps
0x18004d8b5  mov     rdx, rbp; hDC
0x18004d8b8  xor     ecx, ecx; hWnd
0x18004d8ba  mov     ebx, eax
0x18004d8bc  and     ebx, 100h
0x18004d8c2  call    cs:__imp_ReleaseDC
0x18004d8c8  mov     ecx, ebx
0x18004d8ca  neg     ecx
0x18004d8cc  sbb     edx, edx
0x18004d8ce  and     edx, 0FFFFFFFCh
0x18004d8d1  add     edx, 7
0x18004d8d4  mov     [rdi+3C0h], edx
0x18004d8da  test    ebx, ebx
0x18004d8dc  jnz     loc_18004D728
0x18004d8e2  cmp     qword ptr [rdi+3C8h], 0
0x18004d8ea  jz      short loc_18004D936
0x18004d8ec  xor     ebp, ebp
0x18004d8ee  lea     r14d, [rbp+7]
0x18004d8f2  mov     rcx, [rdi+3C8h]; ho
0x18004d8f9  cmp     rbp, rcx
0x18004d8fc  jz      short loc_18004D919
0x18004d8fe  test    rcx, rcx
0x18004d901  jz      short loc_18004D912
0x18004d903  cmp     rcx, cs:?g_hpalHalftone@@3PEAUHPALETTE__@@EA; HPALETTE__ * g_hpalHalftone
0x18004d90a  jz      short loc_18004D912
0x18004d90c  call    cs:__imp_DeleteObject
0x18004d912  mov     [rdi+3C8h], rbp
0x18004d919  mov     [rdi+3C0h], r14d
0x18004d920  jmp     loc_18004D728
0x18004d925  test    r15d, r15d
0x18004d928  jnz     short loc_18004D938
0x18004d92a  xor     edx, edx; int
0x18004d92c  mov     rcx, rdi; this
0x18004d92f  call    ?_RealizeBrowserPalette@CShellBrowser@@AEAAXH@Z; CShellBrowser::_RealizeBrowserPalette(int)
0x18004d934  jmp     short loc_18004D938
0x18004d936  xor     esi, esi
0x18004d938  mov     eax, esi
0x18004d93a  add     rsp, 48h
0x18004d93e  pop     r15
0x18004d940  pop     r14
0x18004d942  pop     rdi
0x18004d943  pop     rsi
0x18004d944  pop     rbp
0x18004d945  pop     rbx
0x18004d946  retn
```
