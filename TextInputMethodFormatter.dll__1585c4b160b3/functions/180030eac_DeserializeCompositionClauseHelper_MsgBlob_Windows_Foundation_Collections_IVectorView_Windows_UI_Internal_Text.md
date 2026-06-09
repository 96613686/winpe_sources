# DeserializeCompositionClauseHelper(MsgBlob *,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause> * *)

- ea: `0x180030eac`
- end: `0x18003112a`
- name: `?DeserializeCompositionClauseHelper@@YAJPEAUMsgBlob@@PEAPEAU?$IVectorView@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180033c80`
- `0x180033fd0`

## callees

- `0x180002264`
- `0x180002270`
- `0x180002294`
- `0x180002f2c`
- `0x1800030e4`
- `0x180012030`
- `0x180014b90`
- `0x180030aac`
- `0x180030eac`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180031052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180031052`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180030ffa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180030ffa`
- `OLEAUT32!__imp_SysFreeString` at `0x180031089`
- `OLEAUT32!__imp_SysFreeString` at `0x180031089`
- `OLEAUT32!__imp_SysStringLen` at `0x180031042`
- `OLEAUT32!__imp_SysStringLen` at `0x180031042`

## string_xrefs

- `0x180030fd2`: `DeserializeForCompositionClause`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeserializeCompositionClauseHelper(_DWORD *a1, __int64 a2)
{
  void *v4; // rax
  __int64 v5; // rax
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int *v8; // rdi
  _QWORD *v9; // r14
  unsigned __int64 v10; // r15
  __int64 v11; // rax
  bool v12; // cf
  unsigned __int64 v13; // rax
  HSTRING v14; // rax
  int v15; // edx
  int v16; // ecx
  unsigned int v17; // edi
  const OLECHAR *v18; // rsi
  unsigned int v19; // r12d
  __int64 v20; // rbx
  const OLECHAR *v21; // rsi
  UINT32 v22; // eax
  int v24; // [rsp+20h] [rbp-30h]
  HSTRING string[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v26; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  __int64 v28; // [rsp+A0h] [rbp+50h]

  v28 = 0;
  v4 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4
    && (v5 = Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>(v4)) != 0 )
  {
    v6 = 0;
    v28 = v5;
  }
  else
  {
    v6 = 2147942414LL;
  }
  if ( (int)v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclient.cpp",
      (const char *)v6,
      v24);
  if ( a1 )
  {
    v7 = *a1 & 0xE0000000;
    if ( v7 == 1610612736 )
    {
      v8 = a1 + 2;
    }
    else
    {
      if ( v7 != -1610612736 )
        __debugbreak();
      v8 = (unsigned int *)*((_QWORD *)a1 + 1);
    }
    v9 = 0;
    if ( (*a1 & 0x1FFFFFFF) != 0 )
    {
      if ( v8 )
      {
        v10 = *v8;
        if ( (_DWORD)v10 )
        {
          v11 = 16 * v10;
          if ( !is_mul_ok(v10, 0x10u) )
            v11 = -1;
          v12 = __CFADD__(v11, 8);
          v13 = v11 + 8;
          if ( v12 )
            v13 = -1;
          v14 = (HSTRING)operator new[](v13);
          string[0] = v14;
          *(_QWORD *)v14 = (unsigned int)v10;
          v9 = v14 + 2;
          `eh vector constructor iterator'(
            v14 + 2,
            0x10u,
            (unsigned int)v10,
            Microsoft::WRL::ComPtr<IUnknown>::ComPtr<IUnknown>,
            (void (*)(void *))TextCompositionClause::~TextCompositionClause);
          if ( v9 )
          {
            v18 = (const OLECHAR *)(v8 + 1);
            v19 = 0;
            do
            {
              v20 = *(unsigned int *)v18;
              v21 = v18 + 2;
              v9[2 * v19] = SysAllocStringLen(v21, v20);
              v9[2 * v19 + 1] = *(_QWORD *)&v21[v20];
              v18 = &v21[v20 + 4];
              ++v19;
            }
            while ( v19 < (unsigned int)v10 );
            v17 = 0;
          }
          else
          {
            if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
              McTemplateU0sqq_EventWriteTransfer(v16, v15, (unsigned int)"DeserializeForCompositionClause", 142, 14);
            v17 = 0;
          }
          do
          {
            *(_OWORD *)string = 0;
            v22 = SysStringLen((BSTR)v9[2 * v17]);
            WindowsCreateString((PCNZWCH)v9[2 * v17], v22, string);
            string[1] = (HSTRING)v9[2 * v17 + 1];
            v26 = *(_OWORD *)string;
            (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v28 + 104LL))(v28, &v26);
            SysFreeString((BSTR)v9[2 * v17]);
            v9[2 * v17++] = 0;
          }
          while ( v17 < (unsigned int)v10 );
        }
      }
    }
    if ( v9 )
    {
      `eh vector destructor iterator'(
        v9,
        0x10u,
        *(v9 - 1),
        (void (*)(void *))TextCompositionClause::~TextCompositionClause);
      operator delete[](v9 - 1, 16LL * *(v9 - 1) + 8);
    }
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 64LL))(v28, a2);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return 0;
}

```

## disassembly

```asm
0x180030eac  mov     [rsp-38h+arg_0], rbx
0x180030eb1  push    rbp
0x180030eb2  push    rsi
0x180030eb3  push    rdi
0x180030eb4  push    r12
0x180030eb6  push    r13
0x180030eb8  push    r14
0x180030eba  push    r15
0x180030ebc  mov     rbp, rsp
0x180030ebf  sub     rsp, 50h
0x180030ec3  mov     r13, rdx
0x180030ec6  mov     rbx, rcx
0x180030ec9  mov     [rbp+arg_10], 0
0x180030ed1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030ed8  mov     ecx, 70h ; 'p'; unsigned __int64
0x180030edd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180030ee2  test    rax, rax
0x180030ee5  jz      short loc_180030EFE
0x180030ee7  mov     rcx, rax
0x180030eea  call    ??0?$Vector@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause> const &,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::permission)
0x180030eef  nop
0x180030ef0  test    rax, rax
0x180030ef3  jz      short loc_180030EFE
0x180030ef5  xor     r9d, r9d
0x180030ef8  mov     [rbp+arg_10], rax
0x180030efc  jmp     short loc_180030F04
0x180030efe  mov     r9d, 8007000Eh; char *
0x180030f04  mov     rcx, [rbp+38h]; this
0x180030f08  test    r9d, r9d
0x180030f0b  js      loc_180031118
0x180030f11  test    rbx, rbx
0x180030f14  jz      loc_1800310CC
0x180030f1a  mov     ecx, [rbx]
0x180030f1c  mov     eax, ecx
0x180030f1e  and     eax, 0E0000000h
0x180030f23  cmp     eax, 60000000h
0x180030f28  jz      short loc_180030F38
0x180030f2a  cmp     eax, 0A0000000h
0x180030f2f  jz      short loc_180030F32
0x180030f31  int     3; Trap to Debugger
0x180030f32  mov     rdi, [rbx+8]
0x180030f36  jmp     short loc_180030F3C
0x180030f38  lea     rdi, [rbx+8]
0x180030f3c  mov     eax, 1FFFFFFFh
0x180030f41  xor     r14d, r14d
0x180030f44  xor     r15d, r15d
0x180030f47  lea     esi, [r14+10h]
0x180030f4b  lea     r12, ??1TextCompositionClause@@QEAA@XZ; TextCompositionClause::~TextCompositionClause(void)
0x180030f52  test    eax, ecx
0x180030f54  jbe     loc_18003102B
0x180030f5a  test    rdi, rdi
0x180030f5d  jz      loc_18003102B
0x180030f63  mov     r15d, [rdi]
0x180030f66  test    r15d, r15d
0x180030f69  jz      loc_18003102B
0x180030f6f  mov     ebx, r15d
0x180030f72  mov     [rbp+arg_18], rbx
0x180030f76  mov     eax, esi
0x180030f78  mul     r15
0x180030f7b  lea     rcx, [rsi-11h]
0x180030f7f  cmovb   rax, rcx
0x180030f83  add     rax, 8
0x180030f87  cmovb   rax, rcx
0x180030f8b  mov     rcx, rax; unsigned __int64
0x180030f8e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180030f93  mov     [rbp+string], rax
0x180030f97  mov     [rax], rbx
0x180030f9a  lea     r14, [rax+8]
0x180030f9e  mov     qword ptr [rsp+50h+var_30], r12; void (*)(void *)
0x180030fa3  lea     r9, ??0?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180030faa  mov     r8d, r15d; unsigned __int64
0x180030fad  mov     edx, esi; unsigned __int64
0x180030faf  mov     rcx, r14; void *
0x180030fb2  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180030fb7  nop
0x180030fb8  test    r14, r14
0x180030fbb  jnz     short loc_180030FE2
0x180030fbd  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180030fc4  jz      short loc_180030FDE
0x180030fc6  mov     [rsp+50h+var_30], 8007000Eh
0x180030fce  lea     r9d, [rsi+7Eh]
0x180030fd2  lea     r8, aDeserializefor; "DeserializeForCompositionClause"
0x180030fd9  call    McTemplateU0sqq_EventWriteTransfer
0x180030fde  xor     edi, edi
0x180030fe0  jmp     short loc_180031032
0x180030fe2  lea     rsi, [rdi+4]
0x180030fe6  xor     r12d, r12d
0x180030fe9  mov     ebx, [rsi]
0x180030feb  add     rsi, 4
0x180030fef  mov     edi, r12d
0x180030ff2  add     rdi, rdi
0x180030ff5  mov     edx, ebx; ui
0x180030ff7  mov     rcx, rsi; strIn
0x180030ffa  call    cs:__imp_SysAllocStringLen
0x180031000  mov     [r14+rdi*8], rax
0x180031004  mov     rax, [rsi+rbx*2]
0x180031008  mov     [r14+rdi*8+8], rax
0x18003100d  lea     rsi, [rsi+rbx*2]
0x180031011  add     rsi, 8
0x180031015  inc     r12d
0x180031018  cmp     r12d, r15d
0x18003101b  jb      short loc_180030FE9
0x18003101d  xor     edi, edi
0x18003101f  lea     esi, [rdi+10h]
0x180031022  lea     r12, ??1TextCompositionClause@@QEAA@XZ; TextCompositionClause::~TextCompositionClause(void)
0x180031029  jmp     short loc_180031032
0x18003102b  xor     edi, edi
0x18003102d  test    r15d, r15d
0x180031030  jz      short loc_18003109E
0x180031032  mov     ebx, edi
0x180031034  add     rbx, rbx
0x180031037  xorps   xmm0, xmm0
0x18003103a  movups  xmmword ptr [rbp+string], xmm0
0x18003103e  mov     rcx, [r14+rbx*8]; pbstr
0x180031042  call    cs:__imp_SysStringLen
0x180031048  lea     r8, [rbp+string]; string
0x18003104c  mov     edx, eax; length
0x18003104e  mov     rcx, [r14+rbx*8]; sourceString
0x180031052  call    cs:__imp_WindowsCreateString
0x180031058  mov     eax, [r14+rbx*8+8]
0x18003105d  mov     dword ptr [rbp+string+8], eax
0x180031060  mov     eax, [r14+rbx*8+0Ch]
0x180031065  mov     dword ptr [rbp+string+0Ch], eax
0x180031068  mov     rcx, [rbp+arg_10]
0x18003106c  movaps  xmm0, xmmword ptr [rbp+string]
0x180031070  movdqa  [rbp+var_10], xmm0
0x180031075  mov     rax, [rcx]
0x180031078  lea     rdx, [rbp+var_10]
0x18003107c  mov     rax, [rax+68h]
0x180031080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031085  mov     rcx, [r14+rbx*8]; bstrString
0x180031089  call    cs:__imp_SysFreeString
0x18003108f  mov     qword ptr [r14+rbx*8], 0
0x180031097  inc     edi
0x180031099  cmp     edi, r15d
0x18003109c  jb      short loc_180031032
0x18003109e  test    r14, r14
0x1800310a1  jz      short loc_1800310CC
0x1800310a3  lea     rbx, [r14-8]
0x1800310a7  mov     r9, r12; void (*)(void *)
0x1800310aa  mov     r8, [rbx]; unsigned __int64
0x1800310ad  mov     rdx, rsi; unsigned __int64
0x1800310b0  mov     rcx, r14; void *
0x1800310b3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800310b8  mov     rdx, [rbx]
0x1800310bb  shl     rdx, 4
0x1800310bf  add     rdx, 8; unsigned __int64
0x1800310c3  mov     rcx, rbx; void *
0x1800310c6  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x1800310cb  nop
0x1800310cc  mov     rcx, [rbp+arg_10]
0x1800310d0  mov     rax, [rcx]
0x1800310d3  mov     rdx, r13
0x1800310d6  mov     rax, [rax+40h]
0x1800310da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310df  nop
0x1800310e0  mov     rcx, [rbp+arg_10]
0x1800310e4  test    rcx, rcx
0x1800310e7  jz      short loc_1800310FE
0x1800310e9  mov     [rbp+arg_10], 0
0x1800310f1  mov     rax, [rcx]
0x1800310f4  mov     rax, [rax+10h]
0x1800310f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310fd  nop
0x1800310fe  xor     eax, eax
0x180031100  mov     rbx, [rsp+50h+arg_0]
0x180031108  add     rsp, 50h
0x18003110c  pop     r15
0x18003110e  pop     r14
0x180031110  pop     r13
0x180031112  pop     r12
0x180031114  pop     rdi
0x180031115  pop     rsi
0x180031116  pop     rbp
0x180031117  retn
0x180031118  lea     r8, aMincoreTextinp_19; "mincore\\textinput\\dev\\virtualization"...
0x18003111f  mov     edx, 0B9h; void *
0x180031124  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
