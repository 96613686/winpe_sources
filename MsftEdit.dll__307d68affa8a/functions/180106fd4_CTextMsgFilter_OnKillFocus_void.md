# CTextMsgFilter::OnKillFocus(void)

- ea: `0x180106fd4`
- end: `0x180107103`
- name: `?OnKillFocus@CTextMsgFilter@@AEAAXXZ`
- size: `303`
- prototype: `void __fastcall(CTextMsgFilter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180069760`

## callees

- `0x18006933c`
- `0x180106fd4`
- `0x1801397b4`
- `0x1801469fc`
- `0x18015c8a0`
- `0x18015f068`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180107021`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180107021`
- `ext-ms-win-imm-l1-1-0!ImmGetOpenStatus` at `0x180107075`
- `ext-ms-win-imm-l1-1-0!ImmGetOpenStatus` at `0x180107075`

## pseudocode

```c
void __fastcall CTextMsgFilter::OnKillFocus(CTextMsgFilter *this)
{
  __int64 v2; // rax
  HKL KeyboardLayout; // rax
  HIMC ImmContext; // rax
  HIMC v5; // rdi
  int OpenStatus; // ecx
  unsigned int v7; // r9d

  if ( *((int *)this + 7) < 0 && (*((_DWORD *)this + 7) & 0x2000) != 0 )
  {
    v2 = *((_QWORD *)this + 14);
    if ( v2 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v2 + 192) + 104LL) + 64LL))(
        *(_QWORD *)(*(_QWORD *)(v2 + 192) + 104LL),
        0);
  }
  if ( (*((_DWORD *)this + 7) & 0x400) != 0 )
  {
    KeyboardLayout = GetKeyboardLayout(0);
    *((_QWORD *)this + 6) = KeyboardLayout;
    if ( CW32System::IsFELCID((unsigned int)KeyboardLayout) )
    {
      ImmContext = LocalGetImmContext(this);
      v5 = ImmContext;
      if ( ImmContext )
      {
        if ( (*((_BYTE *)this + 28) & 0x40) != 0 )
          OpenStatus = (*(__int64 (__fastcall **)(void *, HIMC))(*(_QWORD *)qword_1802DF218 + 264LL))(
                         qword_1802DF218,
                         ImmContext) == 0;
        else
          OpenStatus = ImmGetOpenStatus(ImmContext);
        v7 = *((_DWORD *)this + 7) ^ (*((_DWORD *)this + 7) ^ (OpenStatus << 11)) & 0x800;
        *((_DWORD *)this + 7) = v7;
        if ( (OpenStatus & 1) != 0 )
          CW32System::ImmGetConversionStatus(v5, (unsigned int *)this + 10, (unsigned int *)this + 11, (v7 >> 6) & 1);
        LocalReleaseImmContext(this, v5);
      }
    }
  }
  if ( (*((_DWORD *)this + 7) & 0x30000) != 0 )
    CTextMsgFilter::SetIMESentenceMode(this, 0, 0);
  if ( CW32System::_pIMEShare )
  {
    (*(void (__fastcall **)(struct CIMEShare *))(*(_QWORD *)CW32System::_pIMEShare + 40LL))(CW32System::_pIMEShare);
    CW32System::_pIMEShare = 0;
  }
}

```

## disassembly

```asm
0x180106fd4  mov     [rsp+arg_0], rbx
0x180106fd9  push    rdi
0x180106fda  sub     rsp, 20h
0x180106fde  cmp     dword ptr [rcx+1Ch], 0
0x180106fe2  mov     rbx, rcx
0x180106fe5  jge     short loc_180107012
0x180106fe7  test    dword ptr [rcx+1Ch], 2000h
0x180106fee  jz      short loc_180107012
0x180106ff0  mov     rax, [rcx+70h]
0x180106ff4  test    rax, rax
0x180106ff7  jz      short loc_180107012
0x180106ff9  mov     rax, [rax+0C0h]
0x180107000  xor     edx, edx
0x180107002  mov     rcx, [rax+68h]
0x180107006  mov     rax, [rcx]
0x180107009  mov     rax, [rax+40h]
0x18010700d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107012  test    dword ptr [rbx+1Ch], 400h
0x180107019  jz      loc_1801070BF
0x18010701f  xor     ecx, ecx; idThread
0x180107021  call    cs:__imp_GetKeyboardLayout
0x180107027  mov     ecx, eax; unsigned int
0x180107029  mov     [rbx+30h], rax
0x18010702d  call    ?IsFELCID@CW32System@@SA_NK@Z; CW32System::IsFELCID(ulong)
0x180107032  test    al, al
0x180107034  jz      loc_1801070BF
0x18010703a  mov     rcx, rbx; struct CTextMsgFilter *
0x18010703d  call    ?LocalGetImmContext@@YAPEAUHIMC__@@AEAVCTextMsgFilter@@@Z; LocalGetImmContext(CTextMsgFilter &)
0x180107042  mov     rdi, rax
0x180107045  test    rax, rax
0x180107048  jz      short loc_1801070BF
0x18010704a  test    byte ptr [rbx+1Ch], 40h
0x18010704e  jz      short loc_180107072
0x180107050  mov     rcx, cs:qword_1802DF218
0x180107057  mov     rdx, [rcx]
0x18010705a  mov     rax, [rdx+108h]
0x180107061  mov     rdx, rdi
0x180107064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107069  xor     ecx, ecx
0x18010706b  test    eax, eax
0x18010706d  setz    cl
0x180107070  jmp     short loc_18010707D
0x180107072  mov     rcx, rdi; HIMC
0x180107075  call    cs:__imp_ImmGetOpenStatus
0x18010707b  mov     ecx, eax
0x18010707d  mov     r9d, ecx
0x180107080  shl     r9d, 0Bh
0x180107084  xor     r9d, [rbx+1Ch]
0x180107088  and     r9d, 800h
0x18010708f  xor     r9d, [rbx+1Ch]
0x180107093  mov     [rbx+1Ch], r9d
0x180107097  test    cl, 1
0x18010709a  jz      short loc_1801070B4
0x18010709c  shr     r9d, 6
0x1801070a0  lea     r8, [rbx+2Ch]; unsigned int *
0x1801070a4  and     r9d, 1; int
0x1801070a8  lea     rdx, [rbx+28h]; unsigned int *
0x1801070ac  mov     rcx, rdi; HIMC
0x1801070af  call    ?ImmGetConversionStatus@CW32System@@SAHPEAUHIMC__@@PEAK1H@Z; CW32System::ImmGetConversionStatus(HIMC__ *,ulong *,ulong *,int)
0x1801070b4  mov     rdx, rdi; HIMC
0x1801070b7  mov     rcx, rbx; struct CTextMsgFilter *
0x1801070ba  call    ?LocalReleaseImmContext@@YAXAEAVCTextMsgFilter@@PEAUHIMC__@@@Z; LocalReleaseImmContext(CTextMsgFilter &,HIMC__ *)
0x1801070bf  test    dword ptr [rbx+1Ch], 30000h
0x1801070c6  jz      short loc_1801070D5
0x1801070c8  xor     r8d, r8d; HKL
0x1801070cb  xor     edx, edx; int
0x1801070cd  mov     rcx, rbx; this
0x1801070d0  call    ?SetIMESentenceMode@CTextMsgFilter@@AEAAXHPEAUHKL__@@@Z; CTextMsgFilter::SetIMESentenceMode(int,HKL__ *)
0x1801070d5  mov     rcx, cs:?_pIMEShare@CW32System@@2PEAVCIMEShare@@EA; CIMEShare * CW32System::_pIMEShare
0x1801070dc  test    rcx, rcx
0x1801070df  jz      short loc_1801070F8
0x1801070e1  mov     rax, [rcx]
0x1801070e4  mov     rax, [rax+28h]
0x1801070e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801070ed  mov     cs:?_pIMEShare@CW32System@@2PEAVCIMEShare@@EA, 0; CIMEShare * CW32System::_pIMEShare
0x1801070f8  mov     rbx, [rsp+28h+arg_0]
0x1801070fd  add     rsp, 20h
0x180107101  pop     rdi
0x180107102  retn
```
