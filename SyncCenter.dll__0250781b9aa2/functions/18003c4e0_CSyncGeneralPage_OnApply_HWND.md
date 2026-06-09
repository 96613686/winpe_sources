# CSyncGeneralPage::OnApply(HWND__ *)

- ea: `0x18003c4e0`
- end: `0x18003c62b`
- name: `?OnApply@CSyncGeneralPage@@MEAA_JPEAUHWND__@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(CSyncGeneralPage *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003c4e0`
- `0x18004bcd4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c54f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c54f`
- `USER32!SendMessageW` at `0x18003c4fe`
- `USER32!SendMessageW` at `0x18003c4fe`
- `USER32!SetWindowLongW` at `0x18003c606`
- `USER32!SetWindowLongW` at `0x18003c606`

## pseudocode

```c
__int64 __fastcall CSyncGeneralPage::OnApply(HWND *this, HWND a2)
{
  int v4; // eax
  int v5; // edi
  bool v6; // si
  HWND v7; // r8
  __int64 v8; // rax
  _BOOL8 v9; // rdx
  int v10; // eax
  int v11; // ecx
  HWND v12; // rax
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  v4 = SendMessageW(this[4], 0xF0u, 0, 0);
  v5 = v4;
  if ( v4 != 2 )
  {
    v6 = v4 == 1;
    if ( (v4 == 1) != *((_BYTE *)this[7] + 2872) )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_SyncMgrControl, 0, 0x15u, &GUID_9b63616c_36b2_46bc_959f_c1593952d19b, &ppv) >= 0 )
      {
        v7 = this[7];
        v8 = *(_QWORD *)ppv;
        v9 = v5 == 1;
        if ( *((_BYTE *)this + 48) == 1 )
          v10 = (*(__int64 (__fastcall **)(LPVOID, _BOOL8, HWND, HWND, _DWORD))(v8 + 128))(ppv, v9, v7 + 7, a2, 0);
        else
          v10 = (*(__int64 (__fastcall **)(LPVOID, _BOOL8, HWND, HWND, HWND, _DWORD))(v8 + 136))(
                  ppv,
                  v9,
                  v7 + 7,
                  v7 + 39,
                  a2,
                  0);
        v11 = v10;
        v12 = this[7];
        if ( v11 < 0 )
        {
          CSyncBasePropertyPage::DisplayErrorDialog(
            (CSyncBasePropertyPage *)this,
            a2,
            0xD2Bu,
            0xD2Au,
            v11,
            32,
            v12 + 71);
          SetWindowLongW(a2, 0, 1);
        }
        else
        {
          *((_BYTE *)v12 + 2872) = v6;
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18003c4e0  push    rbx
0x18003c4e2  push    rbp
0x18003c4e3  push    rsi
0x18003c4e4  push    rdi
0x18003c4e5  sub     rsp, 48h
0x18003c4e9  mov     rbp, rdx
0x18003c4ec  mov     rbx, rcx
0x18003c4ef  mov     rcx, [rcx+20h]; hWnd
0x18003c4f3  mov     edx, 0F0h; Msg
0x18003c4f8  xor     r9d, r9d; lParam
0x18003c4fb  xor     r8d, r8d; wParam
0x18003c4fe  call    cs:__imp_SendMessageW
0x18003c504  mov     rdi, rax
0x18003c507  cmp     eax, 2
0x18003c50a  jz      loc_18003C61D
0x18003c510  mov     rcx, [rbx+38h]
0x18003c514  cmp     edi, 1
0x18003c517  setz    sil
0x18003c51b  cmp     sil, [rcx+0B38h]
0x18003c522  jz      loc_18003C61D
0x18003c528  xor     edx, edx; pUnkOuter
0x18003c52a  mov     [rsp+68h+arg_0], 0
0x18003c533  lea     rax, [rsp+68h+arg_0]
0x18003c538  lea     r9, _GUID_9b63616c_36b2_46bc_959f_c1593952d19b; riid
0x18003c53f  mov     [rsp+68h+ppv], rax; ppv
0x18003c544  lea     rcx, CLSID_SyncMgrControl; rclsid
0x18003c54b  lea     r8d, [rdx+15h]; dwClsContext
0x18003c54f  call    cs:__imp_CoCreateInstance
0x18003c555  test    eax, eax
0x18003c557  js      loc_18003C61D
0x18003c55d  mov     rcx, [rsp+68h+arg_0]
0x18003c562  xor     edx, edx
0x18003c564  cmp     byte ptr [rbx+30h], 1
0x18003c568  mov     r8, [rbx+38h]
0x18003c56c  mov     rax, [rcx]
0x18003c56f  jnz     short loc_18003C594
0x18003c571  mov     rax, [rax+80h]
0x18003c578  add     r8, 1Ch
0x18003c57c  cmp     edi, 1
0x18003c57f  mov     dword ptr [rsp+68h+ppv], 0
0x18003c587  mov     r9, rbp
0x18003c58a  setz    dl
0x18003c58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c592  jmp     short loc_18003C5BE
0x18003c594  mov     rax, [rax+88h]
0x18003c59b  lea     r9, [r8+9Ch]
0x18003c5a2  add     r8, 1Ch
0x18003c5a6  mov     [rsp+68h+var_40], 0
0x18003c5ae  cmp     edi, 1
0x18003c5b1  mov     [rsp+68h+ppv], rbp
0x18003c5b6  setz    dl
0x18003c5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5be  mov     ecx, eax
0x18003c5c0  mov     rax, [rbx+38h]
0x18003c5c4  test    ecx, ecx
0x18003c5c6  js      short loc_18003C5D1
0x18003c5c8  mov     [rax+0B38h], sil
0x18003c5cf  jmp     short loc_18003C60C
0x18003c5d1  add     rax, 11Ch
0x18003c5d7  mov     r9d, 0D2Ah; unsigned int
0x18003c5dd  mov     [rsp+68h+var_38], rax
0x18003c5e2  mov     rdx, rbp; HWND
0x18003c5e5  mov     [rsp+68h+var_40], 20h ; ' '; int
0x18003c5ed  mov     dword ptr [rsp+68h+ppv], ecx; int
0x18003c5f1  mov     rcx, rbx; this
0x18003c5f4  lea     r8d, [r9+1]; unsigned int
0x18003c5f8  call    ?DisplayErrorDialog@CSyncBasePropertyPage@@IEAAJPEAUHWND__@@IIJHZZ; CSyncBasePropertyPage::DisplayErrorDialog(HWND__ *,uint,uint,long,int,...)
0x18003c5fd  xor     edx, edx; nIndex
0x18003c5ff  mov     rcx, rbp; hWnd
0x18003c602  lea     r8d, [rdx+1]; dwNewLong
0x18003c606  call    cs:__imp_SetWindowLongW
0x18003c60c  mov     rcx, [rsp+68h+arg_0]
0x18003c611  mov     rdx, [rcx]
0x18003c614  mov     rax, [rdx+10h]
0x18003c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c61d  mov     eax, 1
0x18003c622  add     rsp, 48h
0x18003c626  pop     rdi
0x18003c627  pop     rsi
0x18003c628  pop     rbp
0x18003c629  pop     rbx
0x18003c62a  retn
```
