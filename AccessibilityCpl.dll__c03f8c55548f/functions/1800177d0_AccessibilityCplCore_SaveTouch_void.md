# AccessibilityCplCore::SaveTouch(void)

- ea: `0x1800177d0`
- end: `0x1800178ba`
- name: `?SaveTouch@AccessibilityCplCore@@AEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180002018`
- `0x180002024`
- `0x1800177d0`
- `0x180025a18`
- `0x18002e010`

## import_xrefs

- `USER32!SendMessageW` at `0x180017829`
- `USER32!SendMessageW` at `0x180017844`
- `USER32!SendMessageW` at `0x180017884`
- `USER32!SendMessageW` at `0x180017829`
- `USER32!SendMessageW` at `0x180017844`
- `USER32!SendMessageW` at `0x180017884`
- `DUI70!StrToID` at `0x1800177e8`
- `DUI70!StrToID` at `0x1800177e8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800177f4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800177f4`

## string_xrefs

- `0x1800177e1`: `slatelaunchcombobox`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveTouch(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  void *v2; // rdi
  unsigned __int16 v3; // ax
  struct DirectUI::Element *Descendent; // rax
  HWND v5; // rbp
  int v6; // eax
  WPARAM v7; // rsi
  int v8; // eax
  int v9; // ebx
  void *v10; // rax
  int v11; // eax

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v2 = 0;
  v3 = StrToID(L"slatelaunchcombobox");
  Descendent = DirectUI::Element::FindDescendent(v1, v3);
  if ( Descendent )
  {
    v5 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
    v6 = SendMessageW(v5, 0x147u, 0, 0);
    if ( v6 > 0 )
    {
      v7 = v6;
      v8 = SendMessageW(v5, 0x149u, v6, 0);
      v9 = v8;
      if ( v8 >= 1 )
      {
        v10 = operator new[](saturated_mul(v8 + 1, 2u));
        v2 = v10;
        if ( v10 )
        {
          v11 = SendMessageW(v5, 0x148u, v7, (LPARAM)v10);
          if ( v11 == -1 || v11 != v9 )
          {
            operator delete[](v2);
            v2 = 0;
          }
        }
      }
    }
    SetSlateDefaultAT((unsigned __int16 *)v2);
  }
  operator delete[](v2);
  return 0;
}

```

## disassembly

```asm
0x1800177d0  push    rbx
0x1800177d2  push    rbp
0x1800177d3  push    rsi
0x1800177d4  push    rdi
0x1800177d5  push    r14
0x1800177d7  sub     rsp, 20h
0x1800177db  mov     rbx, [rcx+60h]
0x1800177df  xor     edi, edi
0x1800177e1  lea     rcx, aSlatelaunchcom; "slatelaunchcombobox"
0x1800177e8  call    cs:__imp_StrToID
0x1800177ee  movzx   edx, ax
0x1800177f1  mov     rcx, rbx
0x1800177f4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800177fa  mov     rdx, rax
0x1800177fd  test    rax, rax
0x180017800  jz      loc_1800178A5
0x180017806  mov     rcx, [rax]
0x180017809  mov     rax, [rcx+168h]
0x180017810  mov     rcx, rdx
0x180017813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017818  xor     r9d, r9d; lParam
0x18001781b  xor     r8d, r8d; wParam
0x18001781e  mov     edx, 147h; Msg
0x180017823  mov     rcx, rax; hWnd
0x180017826  mov     rbp, rax
0x180017829  call    cs:__imp_SendMessageW
0x18001782f  test    eax, eax
0x180017831  jle     short loc_18001789D
0x180017833  movsxd  rsi, eax
0x180017836  xor     r9d, r9d; lParam
0x180017839  mov     r8, rsi; wParam
0x18001783c  mov     edx, 149h; Msg
0x180017841  mov     rcx, rbp; hWnd
0x180017844  call    cs:__imp_SendMessageW
0x18001784a  mov     rbx, rax
0x18001784d  cmp     eax, 1
0x180017850  jl      short loc_18001789D
0x180017852  lea     ecx, [rax+1]
0x180017855  movsxd  rdx, ecx
0x180017858  lea     eax, [rdi+2]
0x18001785b  mul     rdx
0x18001785e  lea     r14, [rdi-1]
0x180017862  cmovb   rax, r14
0x180017866  mov     rcx, rax; unsigned __int64
0x180017869  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001786e  mov     rdi, rax
0x180017871  test    rax, rax
0x180017874  jz      short loc_18001789D
0x180017876  mov     r9, rax; lParam
0x180017879  mov     r8, rsi; wParam
0x18001787c  mov     edx, 148h; Msg
0x180017881  mov     rcx, rbp; hWnd
0x180017884  call    cs:__imp_SendMessageW
0x18001788a  cmp     eax, r14d
0x18001788d  jz      short loc_180017893
0x18001788f  cmp     eax, ebx
0x180017891  jz      short loc_18001789D
0x180017893  mov     rcx, rdi; void *
0x180017896  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001789b  xor     edi, edi
0x18001789d  mov     rcx, rdi; unsigned __int16 *
0x1800178a0  call    ?SetSlateDefaultAT@@YAJPEAG@Z; SetSlateDefaultAT(ushort *)
0x1800178a5  mov     rcx, rdi; void *
0x1800178a8  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800178ad  xor     eax, eax
0x1800178af  add     rsp, 20h
0x1800178b3  pop     r14
0x1800178b5  pop     rdi
0x1800178b6  pop     rsi
0x1800178b7  pop     rbp
0x1800178b8  pop     rbx
0x1800178b9  retn
```
