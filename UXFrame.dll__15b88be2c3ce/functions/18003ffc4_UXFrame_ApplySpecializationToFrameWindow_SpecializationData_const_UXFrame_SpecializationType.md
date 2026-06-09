# UXFrame::ApplySpecializationToFrameWindow(SpecializationData const &,UXFrame::SpecializationType)

- ea: `0x18003ffc4`
- end: `0x1800401a5`
- name: `?ApplySpecializationToFrameWindow@UXFrame@@AEAAXAEBUSpecializationData@@W4SpecializationType@1@@Z`
- size: `481`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004a43c`

## callees

- `0x180002b20`
- `0x18001049c`
- `0x180017124`
- `0x18003ffc4`
- `0x180049fe0`
- `0x18005a010`

## import_xrefs

- `USER32!SetWindowPos` at `0x18004016b`
- `USER32!SetWindowPos` at `0x18004016b`
- `USER32!GetWindowBand` at `0x1800400a4`
- `USER32!GetWindowBand` at `0x1800400a4`
- `USER32!SetWindowBand` at `0x1800400d9`
- `USER32!SetWindowBand` at `0x180040108`
- `USER32!SetWindowBand` at `0x18004011f`
- `USER32!SetWindowBand` at `0x1800400d9`
- `USER32!SetWindowBand` at `0x180040108`
- `USER32!SetWindowBand` at `0x18004011f`
- `USER32!SetWindowLongPtrW` at `0x180040025`
- `USER32!SetWindowLongPtrW` at `0x18004004a`
- `USER32!SetWindowLongPtrW` at `0x180040025`
- `USER32!SetWindowLongPtrW` at `0x18004004a`

## string_xrefs

- `0x180040193`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
void __fastcall UXFrame::ApplySpecializationToFrameWindow(__int64 a1, __int64 a2, int a3)
{
  const char *v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // eax
  bool v8; // bl
  __int64 v9; // rax
  HWND v10; // rbp
  HWND v11; // r8
  unsigned int v12; // eax
  unsigned int v13; // [rsp+40h] [rbp-38h] BYREF
  int X; // [rsp+48h] [rbp-30h] BYREF
  int Y; // [rsp+4Ch] [rbp-2Ch]
  int v16; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+54h] [rbp-24h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a3 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 8LL))(*(_QWORD *)(a2 + 32)) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x42C,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
        v5);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 16LL))(*(_QWORD *)(a2 + 32));
    SetWindowLongPtrW(*(HWND *)(a1 + 296), -16, v6);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 24LL))(*(_QWORD *)(a2 + 32));
    SetWindowLongPtrW(*(HWND *)(a1 + 296), -20, v7);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    {
      v8 = ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 24LL))(*(_QWORD *)(a2 + 32)) & 8) != 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 40LL))(*(_QWORD *)(a2 + 32));
      v13 = 0;
      v10 = (HWND)v9;
      if ( v9 )
      {
        GetWindowBand(v9, &v13);
        v12 = v13;
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 48LL))(*(_QWORD *)(a2 + 32));
        v13 = v12;
      }
      if ( v12 >= 2 )
      {
        SetWindowBand(*(_QWORD *)(a1 + 296), 0, v12);
        v8 = 0;
      }
      if ( v10 )
      {
        ShellExperienceHelpers::SetWindowOwner(*(HWND *)(a1 + 296), v10, v11);
      }
      else if ( v8 )
      {
        SetWindowBand(*(_QWORD *)(a1 + 296), 0, 5);
        SetWindowBand(*(_QWORD *)(a1 + 296), -1, 1);
      }
    }
    (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a2 + 32) + 32LL))(*(_QWORD *)(a2 + 32), &X);
    SetWindowPos(*(HWND *)(a1 + 296), 0, X, Y, v16 - X, v17 - Y, 0x34u);
  }
}

```

## disassembly

```asm
0x18003ffc4  test    r8d, r8d
0x18003ffc7  jz      locret_18004018D
0x18003ffcd  mov     [rsp+arg_10], rbx
0x18003ffd2  push    rbp
0x18003ffd3  push    rsi
0x18003ffd4  push    rdi
0x18003ffd5  sub     rsp, 60h
0x18003ffd9  mov     rax, cs:__security_cookie
0x18003ffe0  xor     rax, rsp
0x18003ffe3  mov     [rsp+78h+var_20], rax
0x18003ffe8  mov     rdi, rcx
0x18003ffeb  mov     rsi, rdx
0x18003ffee  mov     rcx, [rdx+20h]
0x18003fff2  mov     rax, [rcx]
0x18003fff5  mov     rax, [rax+8]
0x18003fff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fffe  test    al, al
0x180040000  jz      loc_18004018E
0x180040006  mov     rcx, [rsi+20h]
0x18004000a  mov     rax, [rcx]
0x18004000d  mov     rax, [rax+10h]
0x180040011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040016  mov     rcx, [rdi+128h]; hWnd
0x18004001d  mov     edx, 0FFFFFFF0h; nIndex
0x180040022  mov     r8d, eax; dwNewLong
0x180040025  call    cs:__imp_SetWindowLongPtrW
0x18004002b  mov     rcx, [rsi+20h]
0x18004002f  mov     rax, [rcx]
0x180040032  mov     rax, [rax+18h]
0x180040036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004003b  mov     rcx, [rdi+128h]; hWnd
0x180040042  mov     edx, 0FFFFFFECh; nIndex
0x180040047  mov     r8d, eax; dwNewLong
0x18004004a  call    cs:__imp_SetWindowLongPtrW
0x180040050  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x180040057  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18004005c  test    al, al
0x18004005e  jz      loc_180040125
0x180040064  mov     rcx, [rsi+20h]
0x180040068  mov     rax, [rcx]
0x18004006b  mov     rax, [rax+18h]
0x18004006f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040074  mov     rcx, [rsi+20h]
0x180040078  mov     ebx, eax
0x18004007a  shr     ebx, 3
0x18004007d  and     bl, 1
0x180040080  mov     rdx, [rcx]
0x180040083  mov     rax, [rdx+28h]
0x180040087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004008c  mov     [rsp+78h+var_38], 0
0x180040094  mov     rbp, rax
0x180040097  test    rax, rax
0x18004009a  jz      short loc_1800400B0
0x18004009c  lea     rdx, [rsp+78h+var_38]
0x1800400a1  mov     rcx, rax
0x1800400a4  call    cs:__imp_GetWindowBand
0x1800400aa  mov     eax, [rsp+78h+var_38]
0x1800400ae  jmp     short loc_1800400C4
0x1800400b0  mov     rcx, [rsi+20h]
0x1800400b4  mov     rax, [rcx]
0x1800400b7  mov     rax, [rax+30h]
0x1800400bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400c0  mov     [rsp+78h+var_38], eax
0x1800400c4  test    eax, eax
0x1800400c6  jz      short loc_1800400E1
0x1800400c8  cmp     eax, 1
0x1800400cb  jz      short loc_1800400E1
0x1800400cd  mov     rcx, [rdi+128h]
0x1800400d4  mov     r8d, eax
0x1800400d7  xor     edx, edx
0x1800400d9  call    cs:__imp_SetWindowBand
0x1800400df  xor     bl, bl
0x1800400e1  test    rbp, rbp
0x1800400e4  jz      short loc_1800400F7
0x1800400e6  mov     rcx, [rdi+128h]; hWnd
0x1800400ed  mov     rdx, rbp; hWndInsertAfter
0x1800400f0  call    ?SetWindowOwner@ShellExperienceHelpers@@YAJPEAUHWND__@@0@Z; ShellExperienceHelpers::SetWindowOwner(HWND__ *,HWND__ *)
0x1800400f5  jmp     short loc_180040125
0x1800400f7  test    bl, bl
0x1800400f9  jz      short loc_180040125
0x1800400fb  mov     rcx, [rdi+128h]
0x180040102  xor     edx, edx
0x180040104  lea     r8d, [rdx+5]
0x180040108  call    cs:__imp_SetWindowBand
0x18004010e  mov     rcx, [rdi+128h]
0x180040115  mov     r8d, 1
0x18004011b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004011f  call    cs:__imp_SetWindowBand
0x180040125  mov     rcx, [rsi+20h]
0x180040129  lea     rdx, [rsp+78h+X]
0x18004012e  mov     rax, [rcx]
0x180040131  mov     rax, [rax+20h]
0x180040135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004013a  mov     ecx, [rsp+78h+var_24]
0x18004013e  xor     edx, edx; hWndInsertAfter
0x180040140  mov     r9d, [rsp+78h+Y]; Y
0x180040145  sub     ecx, r9d
0x180040148  mov     eax, [rsp+78h+var_28]
0x18004014c  mov     r8d, [rsp+78h+X]; X
0x180040151  sub     eax, r8d
0x180040154  mov     [rsp+78h+uFlags], 34h ; '4'; uFlags
0x18004015c  mov     [rsp+78h+cy], ecx; cy
0x180040160  mov     rcx, [rdi+128h]; hWnd
0x180040167  mov     [rsp+78h+var_58], eax; cx
0x18004016b  call    cs:__imp_SetWindowPos
0x180040171  mov     rcx, [rsp+78h+var_20]
0x180040176  xor     rcx, rsp; StackCookie
0x180040179  call    __security_check_cookie
0x18004017e  mov     rbx, [rsp+78h+arg_10]
0x180040186  add     rsp, 60h
0x18004018a  pop     rdi
0x18004018b  pop     rsi
0x18004018c  pop     rbp
0x18004018d  retn
0x18004018e  mov     rcx, [rsp+78h]; this
0x180040193  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004019a  mov     edx, 42Ch; void *
0x18004019f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
