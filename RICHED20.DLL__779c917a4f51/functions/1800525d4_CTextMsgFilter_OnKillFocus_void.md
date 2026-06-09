# CTextMsgFilter::OnKillFocus(void)

- ea: `0x1800525d4`
- end: `0x1800526d0`
- name: `?OnKillFocus@CTextMsgFilter@@AEAAXXZ`
- size: `252`
- prototype: `void __fastcall(CTextMsgFilter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180036050`

## callees

- `0x18003ec34`
- `0x180048b80`
- `0x1800525d4`
- `0x18008e89c`
- `0x18008e920`
- `0x18008eb50`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18005265d`: `ImmGetOpenStatus`

## pseudocode

```c
void __fastcall CTextMsgFilter::OnKillFocus(CTextMsgFilter *this)
{
  HKL KeyboardLayout; // rax
  unsigned int Context; // edi
  unsigned __int16 v4; // dx
  __int64 (__fastcall *v5)(_QWORD); // rax
  unsigned int v6; // ecx

  if ( *((_QWORD *)this + 2) )
  {
    if ( (*((_WORD *)this + 16) & 0x400) != 0 )
    {
      KeyboardLayout = CW32System::GetKeyboardLayout(0xFFFFFFFF);
      *((_QWORD *)this + 6) = KeyboardLayout;
      if ( CW32System::IsFELCID((unsigned __int16)KeyboardLayout) )
      {
        Context = CW32System::ImmGetContext(*((HWND *)this + 2));
        if ( Context )
        {
          if ( (*((_BYTE *)this + 32) & 0x40) != 0 )
          {
            v4 = (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800A44B8 + 264LL))(
                   qword_1800A44B8,
                   Context) == 0;
          }
          else
          {
            v5 = (__int64 (__fastcall *)(_QWORD))qword_1800A4160;
            if ( !qword_1800A4160 )
            {
              SetIMEProcAddr((FARPROC *)&qword_1800A4160, 0, "ImmGetOpenStatus");
              v5 = (__int64 (__fastcall *)(_QWORD))qword_1800A4160;
            }
            v4 = v5(Context);
          }
          v6 = v4;
          LOWORD(v6) = *((_WORD *)this + 16) ^ (*((_WORD *)this + 16) ^ (v4 << 11)) & 0x800;
          *((_WORD *)this + 16) = v6;
          if ( (v4 & 1) != 0 )
            CW32System::ImmGetConversionStatus(
              Context,
              (unsigned int *)this + 9,
              (unsigned int *)this + 10,
              (v6 >> 6) & 1);
          CW32System::ImmReleaseContext(*((HWND *)this + 2), Context);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800525d4  mov     [rsp+arg_0], rbx
0x1800525d9  push    rdi
0x1800525da  sub     rsp, 20h
0x1800525de  cmp     qword ptr [rcx+10h], 0
0x1800525e3  mov     rbx, rcx
0x1800525e6  jz      loc_1800526C5
0x1800525ec  mov     eax, 400h
0x1800525f1  test    [rcx+20h], ax
0x1800525f5  jz      loc_1800526C5
0x1800525fb  or      ecx, 0FFFFFFFFh; unsigned int
0x1800525fe  call    ?GetKeyboardLayout@CW32System@@SAPEAUHKL__@@K@Z; CW32System::GetKeyboardLayout(ulong)
0x180052603  movzx   ecx, ax; unsigned int
0x180052606  mov     [rbx+30h], rax
0x18005260a  call    ?IsFELCID@CW32System@@SA_NK@Z; CW32System::IsFELCID(ulong)
0x18005260f  test    al, al
0x180052611  jz      loc_1800526C5
0x180052617  mov     rcx, [rbx+10h]; HWND
0x18005261b  call    ?ImmGetContext@CW32System@@SAKPEAUHWND__@@@Z; CW32System::ImmGetContext(HWND__ *)
0x180052620  mov     edi, eax
0x180052622  test    eax, eax
0x180052624  jz      loc_1800526C5
0x18005262a  test    byte ptr [rbx+20h], 40h
0x18005262e  jz      short loc_180052651
0x180052630  mov     rcx, cs:qword_1800A44B8
0x180052637  mov     rdx, [rcx]
0x18005263a  mov     rax, [rdx+108h]
0x180052641  mov     edx, edi
0x180052643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052648  xor     edx, edx
0x18005264a  test    eax, eax
0x18005264c  setz    dl
0x18005264f  jmp     short loc_180052682
0x180052651  mov     rax, cs:qword_1800A4160
0x180052658  test    rax, rax
0x18005265b  jnz     short loc_180052679
0x18005265d  lea     r8, aImmgetopenstat; "ImmGetOpenStatus"
0x180052664  xor     edx, edx
0x180052666  lea     rcx, qword_1800A4160
0x18005266d  call    SetIMEProcAddr
0x180052672  mov     rax, cs:qword_1800A4160
0x180052679  mov     ecx, edi
0x18005267b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052680  mov     edx, eax
0x180052682  movzx   ecx, dx
0x180052685  mov     eax, 800h
0x18005268a  shl     cx, 0Bh
0x18005268e  xor     cx, [rbx+20h]
0x180052692  and     cx, ax
0x180052695  xor     cx, [rbx+20h]
0x180052699  mov     [rbx+20h], cx
0x18005269d  test    dl, 1
0x1800526a0  jz      short loc_1800526BA
0x1800526a2  shr     ecx, 6
0x1800526a5  lea     r8, [rbx+28h]; unsigned int *
0x1800526a9  and     ecx, 1
0x1800526ac  lea     rdx, [rbx+24h]; unsigned int *
0x1800526b0  mov     r9d, ecx; int
0x1800526b3  mov     ecx, edi; unsigned int
0x1800526b5  call    ?ImmGetConversionStatus@CW32System@@SAHKPEAK0H@Z; CW32System::ImmGetConversionStatus(ulong,ulong *,ulong *,int)
0x1800526ba  mov     rcx, [rbx+10h]; HWND
0x1800526be  mov     edx, edi; unsigned int
0x1800526c0  call    ?ImmReleaseContext@CW32System@@SAHPEAUHWND__@@K@Z; CW32System::ImmReleaseContext(HWND__ *,ulong)
0x1800526c5  mov     rbx, [rsp+28h+arg_0]
0x1800526ca  add     rsp, 20h
0x1800526ce  pop     rdi
0x1800526cf  retn
```
