# ATL::AtlAxWindowProc2

- ea: `0x18000ab80`
- end: `0x18000af29`
- name: `ATL::AtlAxWindowProc2`
- size: `937`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001800`
- `0x180005704`
- `0x18000ab80`
- `0x18000f674`
- `0x180011ce0`
- `0x180032a50`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ae95`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000aef4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ae95`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000aef4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aca7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aca7`
- `KERNEL32!GlobalUnlock` at `0x18000ad55`
- `KERNEL32!GlobalUnlock` at `0x18000ad55`
- `KERNEL32!GlobalLock` at `0x18000ad37`
- `KERNEL32!GlobalLock` at `0x18000ad37`
- `KERNEL32!GlobalAlloc` at `0x18000ad26`
- `KERNEL32!GlobalAlloc` at `0x18000ad26`
- `ole32!CreateStreamOnHGlobal` at `0x18000ad67`
- `ole32!CreateStreamOnHGlobal` at `0x18000ad67`
- `ole32!OleInitialize` at `0x18000ac43`
- `ole32!OleInitialize` at `0x18000ac43`
- `ole32!OleUninitialize` at `0x18000ac36`
- `ole32!OleUninitialize` at `0x18000ac36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad8a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae10`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aecb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad8a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae10`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aecb`
- `USER32!SetWindowLongPtrW` at `0x18000aeac`
- `USER32!SetWindowLongPtrW` at `0x18000aeac`
- `USER32!GetWindowLongPtrW` at `0x18000ac19`
- `USER32!GetWindowLongPtrW` at `0x18000ac19`
- `USER32!DefWindowProcW` at `0x18000af06`
- `USER32!DefWindowProcW` at `0x18000af06`
- `USER32!SetWindowLongW` at `0x18000ac09`
- `USER32!SetWindowLongW` at `0x18000ac09`
- `USER32!GetWindowLongW` at `0x18000abe1`
- `USER32!GetWindowLongW` at `0x18000abf9`
- `USER32!GetWindowLongW` at `0x18000abe1`
- `USER32!GetWindowLongW` at `0x18000abf9`
- `USER32!SetWindowTextW` at `0x18000acee`
- `USER32!SetWindowTextW` at `0x18000acee`
- `USER32!GetWindowTextW` at `0x18000acde`
- `USER32!GetWindowTextW` at `0x18000acde`
- `USER32!GetWindowTextLengthW` at `0x18000ac4c`
- `USER32!GetWindowTextLengthW` at `0x18000ac4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LRESULT __fastcall ATL::AtlAxWindowProc2(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  LONG WindowLongW; // eax
  LONG_PTR WindowLongPtrW; // rax
  int v10; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rsi
  WCHAR *v16; // rax
  int v18; // eax
  unsigned __int16 *v19; // rcx
  SIZE_T v20; // rbx
  struct IStream *v21; // rcx
  HGLOBAL v22; // rax
  void *v23; // rdi
  ATL::Checked *v24; // rax
  OLECHAR *v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // [rsp+0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+20h] [rbp-10h]
  WCHAR String[4]; // [rsp+30h] [rbp+0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp+8h] BYREF
  __int64 v31; // [rsp+40h] [rbp+10h]
  LONG_PTR dwNewLong[3]; // [rsp+48h] [rbp+18h] BYREF

  if ( Msg == 1 )
  {
    OleInitialize(0);
    v10 = GetWindowTextLengthW(hWnd) + 1;
    v11 = 2LL * v10;
    v12 = (v11 + 16) & -(__int64)(v11 < v11 + 16);
    if ( v12 )
    {
      if ( v12 > 0x400 )
      {
        v16 = (WCHAR *)malloc((v11 + 16) & -(__int64)(v11 < v11 + 16));
        v15 = v16;
        if ( !v16 )
          goto LABEL_20;
        *(_DWORD *)v16 = 56797;
        goto LABEL_18;
      }
      v13 = v12 + 15;
      if ( v12 + 15 < v12 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
      v15 = String;
      if ( &v27 != (__int64 *)-48LL )
      {
        wcscpy(String, L"쳌");
LABEL_18:
        v15 += 8;
      }
    }
    else
    {
      v15 = 0;
    }
LABEL_20:
    dwNewLong[1] = (LONG_PTR)v15;
    if ( !v15 )
      return -1;
    GetWindowTextW(hWnd, v15, v10);
    SetWindowTextW(hWnd, &::String);
    dwNewLong[0] = 0;
    v18 = 0;
    if ( lParam && (v19 = *(unsigned __int16 **)lParam) != 0 )
    {
      v18 = *v19;
      v20 = *v19;
    }
    else
    {
      v20 = 0;
    }
    v21 = 0;
    *(_QWORD *)String = 0;
    if ( v18 )
    {
      v22 = GlobalAlloc(0x42u, v20);
      v23 = v22;
      if ( !v22 )
      {
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
LABEL_47:
        if ( *((_DWORD *)v15 - 4) == 56797 )
          free(v15 - 8);
        return -1;
      }
      v24 = (ATL::Checked *)GlobalLock(v22);
      ATL::Checked::memcpy_s(v24, (void *)v20, *(_QWORD *)lParam + 2LL, (const void *)v20, v28);
      GlobalUnlock(v23);
      CreateStreamOnHGlobal(v23, 1, (LPSTREAM *)String);
      v21 = *(struct IStream **)String;
    }
    bstrString = 0;
    if ( (int)ATL::_DialogSplitHelper::ParseInitData(v21, &bstrString) >= 0 )
    {
      dwNewLong[2] = 0;
      v31 = 0;
      v25 = bstrString;
      if ( (int)AtlAxCreateControlLic(v15, (__int64)bstrString) >= 0 )
      {
        v26 = v31;
        if ( (**(int (__fastcall ***)(__int64, GUID *, LONG_PTR *))v31)(
               v31,
               &GUID_3935bda8_4ed9_495c_8650_e01fc1e38a4b,
               dwNewLong) >= 0 )
        {
          SetWindowLongPtrW(hWnd, -21, dwNewLong[0]);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          SysFreeString(v25);
          if ( *(_QWORD *)String )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
          if ( *((_DWORD *)v15 - 4) == 56797 )
            free(v15 - 8);
          return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
        }
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        SysFreeString(v25);
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
      }
      else
      {
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        SysFreeString(v25);
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
      }
    }
    else
    {
      SysFreeString(bstrString);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
    }
    goto LABEL_47;
  }
  if ( Msg == 130 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
    if ( WindowLongPtrW )
      (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
    OleUninitialize();
  }
  else if ( Msg == 528 && (_DWORD)wParam == 1 && (GetWindowLongW(lParam, -20) & 0x10000) != 0 )
  {
    WindowLongW = GetWindowLongW(hWnd, -20);
    SetWindowLongW(hWnd, -20, WindowLongW | 0x10000);
  }
  return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x18000ab80  push    rbp
0x18000ab82  push    rbx
0x18000ab83  push    rsi
0x18000ab84  push    rdi
0x18000ab85  push    r12
0x18000ab87  push    r13
0x18000ab89  push    r14
0x18000ab8b  push    r15
0x18000ab8d  sub     rsp, 78h
0x18000ab91  lea     rbp, [rsp+30h]
0x18000ab96  mov     rax, cs:__security_cookie
0x18000ab9d  xor     rax, rbp
0x18000aba0  mov     [rbp+80h+var_50], rax
0x18000aba4  mov     r15, r9
0x18000aba7  mov     r12, r8
0x18000abaa  mov     r13d, edx
0x18000abad  mov     r14, rcx
0x18000abb0  mov     eax, edx
0x18000abb2  sub     eax, 1
0x18000abb5  jz      loc_18000AC41
0x18000abbb  sub     eax, 81h
0x18000abc0  jz      short loc_18000AC14
0x18000abc2  cmp     eax, 18Eh
0x18000abc7  jnz     loc_18000AEFA
0x18000abcd  cmp     r12d, 1
0x18000abd1  jnz     loc_18000AEFA
0x18000abd7  lea     ebx, [r12-15h]
0x18000abdc  mov     edx, ebx; nIndex
0x18000abde  mov     rcx, r9; hWnd
0x18000abe1  call    cs:__imp_GetWindowLongW
0x18000abe7  mov     edi, 10000h
0x18000abec  test    edi, eax
0x18000abee  jz      loc_18000AEFA
0x18000abf4  mov     edx, ebx; nIndex
0x18000abf6  mov     rcx, r14; hWnd
0x18000abf9  call    cs:__imp_GetWindowLongW
0x18000abff  or      eax, edi
0x18000ac01  mov     r8d, eax; dwNewLong
0x18000ac04  mov     edx, ebx; nIndex
0x18000ac06  mov     rcx, r14; hWnd
0x18000ac09  call    cs:__imp_SetWindowLongW
0x18000ac0f  jmp     loc_18000AEFA
0x18000ac14  mov     edx, 0FFFFFFEBh; nIndex
0x18000ac19  call    cs:__imp_GetWindowLongPtrW
0x18000ac1f  mov     rdx, rax
0x18000ac22  test    rax, rax
0x18000ac25  jz      short loc_18000AC36
0x18000ac27  mov     rcx, [rax]
0x18000ac2a  mov     rax, [rcx+10h]
0x18000ac2e  mov     rcx, rdx
0x18000ac31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac36  call    cs:__imp_OleUninitialize
0x18000ac3c  jmp     loc_18000AEFA
0x18000ac41  xor     ecx, ecx; pvReserved
0x18000ac43  call    cs:__imp_OleInitialize
0x18000ac49  mov     rcx, r14; hWnd
0x18000ac4c  call    cs:__imp_GetWindowTextLengthW
0x18000ac52  lea     ebx, [rax+1]
0x18000ac55  movsxd  rax, ebx
0x18000ac58  add     rax, rax
0x18000ac5b  lea     rcx, [rax+10h]
0x18000ac5f  cmp     rax, rcx
0x18000ac62  sbb     rdx, rdx
0x18000ac65  and     rdx, rcx
0x18000ac68  jz      short loc_18000ACC1
0x18000ac6a  cmp     rdx, 400h
0x18000ac71  ja      short loc_18000ACA4
0x18000ac73  lea     rax, [rdx+0Fh]
0x18000ac77  cmp     rax, rdx
0x18000ac7a  ja      short loc_18000AC86
0x18000ac7c  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000ac86  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000ac8a  call    _alloca_probe
0x18000ac8f  sub     rsp, rax
0x18000ac92  lea     rsi, [rsp+0B0h+String]
0x18000ac97  test    rsi, rsi
0x18000ac9a  jz      short loc_18000ACC3
0x18000ac9c  mov     dword ptr [rsi], 0CCCCh
0x18000aca2  jmp     short loc_18000ACBB
0x18000aca4  mov     rcx, rdx; Size
0x18000aca7  call    cs:__imp_malloc
0x18000acad  mov     rsi, rax
0x18000acb0  test    rax, rax
0x18000acb3  jz      short loc_18000ACC3
0x18000acb5  mov     dword ptr [rax], 0DDDDh
0x18000acbb  add     rsi, 10h
0x18000acbf  jmp     short loc_18000ACC3
0x18000acc1  xor     esi, esi
0x18000acc3  mov     [rbp+80h+var_60], rsi
0x18000acc7  test    rsi, rsi
0x18000acca  jnz     short loc_18000ACD5
0x18000accc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000acd0  jmp     loc_18000AF0C
0x18000acd5  mov     r8d, ebx; nMaxCount
0x18000acd8  mov     rdx, rsi; lpString
0x18000acdb  mov     rcx, r14; hWnd
0x18000acde  call    cs:__imp_GetWindowTextW
0x18000ace4  lea     rdx, String; lpString
0x18000aceb  mov     rcx, r14; hWnd
0x18000acee  call    cs:__imp_SetWindowTextW
0x18000acf4  mov     [rbp+80h+dwNewLong], 0
0x18000acfc  xor     eax, eax
0x18000acfe  test    r15, r15
0x18000ad01  jz      short loc_18000AD12
0x18000ad03  mov     rcx, [r15]
0x18000ad06  test    rcx, rcx
0x18000ad09  jz      short loc_18000AD12
0x18000ad0b  movzx   eax, word ptr [rcx]
0x18000ad0e  mov     ebx, eax
0x18000ad10  jmp     short loc_18000AD14
0x18000ad12  xor     ebx, ebx
0x18000ad14  xor     ecx, ecx
0x18000ad16  mov     qword ptr [rbp+80h+String], rcx
0x18000ad1a  test    eax, eax
0x18000ad1c  jz      short loc_18000AD71
0x18000ad1e  mov     rdx, rbx; dwBytes
0x18000ad21  mov     ecx, 42h ; 'B'; uFlags
0x18000ad26  call    cs:__imp_GlobalAlloc
0x18000ad2c  mov     rdi, rax
0x18000ad2f  test    rax, rax
0x18000ad32  jz      short loc_18000ADAC
0x18000ad34  mov     rcx, rax; hMem
0x18000ad37  call    cs:__imp_GlobalLock
0x18000ad3d  mov     r8, [r15]
0x18000ad40  add     r8, 2; unsigned __int64
0x18000ad44  mov     r9, rbx; void *
0x18000ad47  mov     rdx, rbx; void *
0x18000ad4a  mov     rcx, rax; this
0x18000ad4d  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18000ad52  mov     rcx, rdi; hMem
0x18000ad55  call    cs:__imp_GlobalUnlock
0x18000ad5b  lea     r8, [rbp+80h+String]; ppstm
0x18000ad5f  mov     edx, 1; fDeleteOnRelease
0x18000ad64  mov     rcx, rdi; hGlobal
0x18000ad67  call    cs:__imp_CreateStreamOnHGlobal
0x18000ad6d  mov     rcx, qword ptr [rbp+80h+String]; struct IStream *
0x18000ad71  mov     [rbp+80h+bstrString], 0
0x18000ad79  lea     rdx, [rbp+80h+bstrString]; unsigned __int16 **
0x18000ad7d  call    ?ParseInitData@_DialogSplitHelper@ATL@@SAJPEAUIStream@@PEAPEAG@Z; ATL::_DialogSplitHelper::ParseInitData(IStream *,ushort * *)
0x18000ad82  test    eax, eax
0x18000ad84  jns     short loc_18000ADC7
0x18000ad86  mov     rcx, [rbp+80h+bstrString]; bstrString
0x18000ad8a  call    cs:__imp_SysFreeString
0x18000ad90  nop
0x18000ad91  mov     rcx, qword ptr [rbp+80h+String]
0x18000ad95  test    rcx, rcx
0x18000ad98  jz      short loc_18000ADA7
0x18000ad9a  mov     rax, [rcx]
0x18000ad9d  mov     rax, [rax+10h]
0x18000ada1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada6  nop
0x18000ada7  jmp     loc_18000AE85
0x18000adac  mov     rcx, qword ptr [rbp+80h+String]
0x18000adb0  test    rcx, rcx
0x18000adb3  jz      short loc_18000ADC2
0x18000adb5  mov     rax, [rcx]
0x18000adb8  mov     rax, [rax+10h]
0x18000adbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc1  nop
0x18000adc2  jmp     loc_18000AE85
0x18000adc7  mov     [rbp+80h+var_58], 0
0x18000adcf  mov     [rbp+80h+var_70], 0
0x18000add7  mov     rdi, [rbp+80h+bstrString]
0x18000addb  mov     [rsp+0B0h+var_90], rdi; __int64
0x18000ade0  lea     r9, [rbp+80h+var_70]
0x18000ade4  mov     r8, qword ptr [rbp+80h+String]
0x18000ade8  mov     rdx, r14
0x18000adeb  mov     rcx, rsi; psz
0x18000adee  call    AtlAxCreateControlLic
0x18000adf3  test    eax, eax
0x18000adf5  jns     short loc_18000AE2F
0x18000adf7  mov     rcx, [rbp+80h+var_70]
0x18000adfb  test    rcx, rcx
0x18000adfe  jz      short loc_18000AE0D
0x18000ae00  mov     rax, [rcx]
0x18000ae03  mov     rax, [rax+10h]
0x18000ae07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae0c  nop
0x18000ae0d  mov     rcx, rdi; bstrString
0x18000ae10  call    cs:__imp_SysFreeString
0x18000ae16  nop
0x18000ae17  mov     rcx, qword ptr [rbp+80h+String]
0x18000ae1b  test    rcx, rcx
0x18000ae1e  jz      short loc_18000AE2D
0x18000ae20  mov     rax, [rcx]
0x18000ae23  mov     rax, [rax+10h]
0x18000ae27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae2c  nop
0x18000ae2d  jmp     short loc_18000AE85
0x18000ae2f  mov     rbx, [rbp+80h+var_70]
0x18000ae33  mov     rax, [rbx]
0x18000ae36  lea     r8, [rbp+80h+dwNewLong]
0x18000ae3a  lea     rdx, _GUID_3935bda8_4ed9_495c_8650_e01fc1e38a4b
0x18000ae41  mov     rcx, rbx
0x18000ae44  mov     rax, [rax]
0x18000ae47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4c  test    eax, eax
0x18000ae4e  jns     short loc_18000AEA0
0x18000ae50  test    rbx, rbx
0x18000ae53  jz      short loc_18000AE65
0x18000ae55  mov     rax, [rbx]
0x18000ae58  mov     rcx, rbx
0x18000ae5b  mov     rax, [rax+10h]
0x18000ae5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae64  nop
0x18000ae65  mov     rcx, rdi; bstrString
0x18000ae68  call    cs:__imp_SysFreeString
0x18000ae6e  nop
0x18000ae6f  mov     rcx, qword ptr [rbp+80h+String]
0x18000ae73  test    rcx, rcx
0x18000ae76  jz      short loc_18000AE85
0x18000ae78  mov     rax, [rcx]
0x18000ae7b  mov     rax, [rax+10h]
0x18000ae7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae84  nop
0x18000ae85  lea     rcx, [rsi-10h]; Block
0x18000ae89  cmp     dword ptr [rcx], 0DDDDh
0x18000ae8f  jnz     loc_18000ACCC
0x18000ae95  call    cs:__imp_free
0x18000ae9b  jmp     loc_18000ACCC
0x18000aea0  mov     r8, [rbp+80h+dwNewLong]; dwNewLong
0x18000aea4  mov     edx, 0FFFFFFEBh; nIndex
0x18000aea9  mov     rcx, r14; hWnd
0x18000aeac  call    cs:__imp_SetWindowLongPtrW
0x18000aeb2  nop
0x18000aeb3  test    rbx, rbx
0x18000aeb6  jz      short loc_18000AEC8
0x18000aeb8  mov     rax, [rbx]
0x18000aebb  mov     rcx, rbx
0x18000aebe  mov     rax, [rax+10h]
0x18000aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec7  nop
0x18000aec8  mov     rcx, rdi; bstrString
0x18000aecb  call    cs:__imp_SysFreeString
0x18000aed1  nop
0x18000aed2  mov     rcx, qword ptr [rbp+80h+String]
0x18000aed6  test    rcx, rcx
0x18000aed9  jz      short loc_18000AEE8
0x18000aedb  mov     rax, [rcx]
0x18000aede  mov     rax, [rax+10h]
0x18000aee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee7  nop
0x18000aee8  lea     rcx, [rsi-10h]; Block
0x18000aeec  cmp     dword ptr [rcx], 0DDDDh
0x18000aef2  jnz     short loc_18000AEFA
0x18000aef4  call    cs:__imp_free
0x18000aefa  mov     r9, r15; lParam
0x18000aefd  mov     r8, r12; wParam
0x18000af00  mov     edx, r13d; Msg
0x18000af03  mov     rcx, r14; hWnd
0x18000af06  call    cs:__imp_DefWindowProcW
0x18000af0c  mov     rcx, [rbp+80h+var_50]
0x18000af10  xor     rcx, rbp; StackCookie
0x18000af13  call    __security_check_cookie
0x18000af18  lea     rsp, [rbp+48h]
0x18000af1c  pop     r15
0x18000af1e  pop     r14
0x18000af20  pop     r13
0x18000af22  pop     r12
0x18000af24  pop     rdi
0x18000af25  pop     rsi
0x18000af26  pop     rbx
0x18000af27  pop     rbp
0x18000af28  retn
```
