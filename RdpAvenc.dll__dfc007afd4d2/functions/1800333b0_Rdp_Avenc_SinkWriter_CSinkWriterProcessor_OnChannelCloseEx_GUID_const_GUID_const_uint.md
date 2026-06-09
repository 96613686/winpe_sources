# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelCloseEx(_GUID const &,_GUID const &,uint)

- ea: `0x1800333b0`
- end: `0x18003367d`
- name: `?OnChannelCloseEx@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJAEBU_GUID@@0I@Z`
- size: `717`
- prototype: `int(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001008`
- `0x1800203d4`
- `0x1800241ac`
- `0x1800333b0`
- `0x180089010`

## string_xrefs

- `0x180033523`: `Failed to stop FileIo graphics read channel`
- `0x1800334c0`: `Failed to stop FileIo graphics write channel`
- `0x18003340c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x18003344c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x1800335b5`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x1800335fe`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x1800333f9`: `Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelCloseEx`
- `0x1800335a1`: `Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelCloseEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelCloseEx(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const char *a4)
{
  unsigned int v4; // r14d
  const char *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  __int64 result; // rax
  char *v11; // [rsp+28h] [rbp-60h]
  int v12; // [rsp+40h] [rbp-48h] BYREF
  const char *v13; // [rsp+48h] [rbp-40h] BYREF
  const char *v14; // [rsp+50h] [rbp-38h] BYREF
  _QWORD v15[6]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    v4 = (unsigned int)a4;
    if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_AvencFileIoChannelGraphics )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        v13 = "Closing FileIo graphics channel";
        v14 = "Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelCloseEx";
        v12 = 463;
        v15[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800AEE17,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)v15,
          (__int64)&v12,
          (__int64)&v14,
          (__int64)&v13);
      }
      if ( v4 < 2 )
      {
        v6 = (const char *)(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 40LL))(*((_QWORD *)this + 25));
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
          v6,
          (int)"Failed to stop FileIo graphics read channel",
          v11);
        v8 = *((_QWORD *)this + 25);
        *((_QWORD *)this + 25) = 0;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      else if ( v4 == 2 )
      {
        v6 = (const char *)(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 40LL))(*((_QWORD *)this + 24));
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x1E6,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
          v6,
          (int)"Failed to stop FileIo graphics write channel",
          v11);
        v7 = *((_QWORD *)this + 24);
        *((_QWORD *)this + 24) = 0;
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        LODWORD(v6) = -2147467259;
        LODWORD(v11) = v4;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unknown FileIo graphics channel instance id: %d",
          v11);
      }
      return (unsigned int)v6;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_AvencFileIoChannelCursor.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_AvencFileIoChannelCursor.Data4 )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        v15[0] = "Closing FileIo cursor channel";
        v14 = "Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelCloseEx";
        v12 = 499;
        v13 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800AEDDC,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)&v13,
          (__int64)&v12,
          (__int64)&v14,
          (__int64)v15);
      }
      v6 = (const char *)(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 40LL))(*((_QWORD *)this + 26));
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        v6,
        (int)"Failed to stop FileIo cursor channel",
        v11);
      v9 = (_QWORD *)*((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = 0;
      if ( v9 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v9 + 16LL))(v9, *v9);
      return (unsigned int)v6;
    }
    result = 2147500037LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x203,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800333b0  mov     r11, rsp
0x1800333b3  push    rbx
0x1800333b4  push    rsi
0x1800333b5  push    rdi
0x1800333b6  push    r14
0x1800333b8  sub     rsp, 68h
0x1800333bc  mov     r14d, r9d
0x1800333bf  mov     rsi, rcx
0x1800333c2  mov     rax, [rdx]
0x1800333c5  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data1
0x1800333cc  jnz     loc_180033569
0x1800333d2  mov     rax, [rdx+8]
0x1800333d6  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data4
0x1800333dd  jnz     loc_180033569
0x1800333e3  mov     eax, cs:dword_1800C1058
0x1800333e9  cmp     eax, 4
0x1800333ec  jbe     short loc_18003344C
0x1800333ee  lea     rax, aClosingFileioG; "Closing FileIo graphics channel"
0x1800333f5  mov     [r11-40h], rax
0x1800333f9  lea     rax, aRdpAvencSinkwr_4; "Rdp::Avenc::SinkWriter::CSinkWriterProc"...
0x180033400  mov     [r11-38h], rax
0x180033404  mov     [rsp+88h+var_48], 1CFh
0x18003340c  lea     rdi, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180033413  mov     [r11-30h], rdi
0x180033417  lea     rax, [r11-40h]
0x18003341b  mov     [r11-50h], rax
0x18003341f  lea     rax, [r11-38h]
0x180033423  mov     [r11-58h], rax
0x180033427  lea     rax, [r11-48h]
0x18003342b  mov     [r11-60h], rax
0x18003342f  lea     rax, [r11-30h]
0x180033433  mov     [r11-68h], rax
0x180033437  lea     rdx, byte_1800AEE17
0x18003343e  lea     rcx, dword_1800C1058
0x180033445  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003344a  jmp     short loc_180033453
0x18003344c  lea     rdi, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180033453  mov     eax, r14d
0x180033456  test    r14d, r14d
0x180033459  jz      loc_180033506
0x18003345f  sub     eax, 1
0x180033462  jz      loc_180033506
0x180033468  cmp     eax, 1
0x18003346b  jz      short loc_1800334A3
0x18003346d  mov     ebx, 80004005h
0x180033472  mov     rcx, [rsp+88h]; this
0x18003347a  mov     dword ptr [rsp+88h+var_60], r14d; char *
0x18003347f  lea     rax, aUnknownFileioG; "Unknown FileIo graphics channel instanc"...
0x180033486  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003348b  mov     r9d, 8000FFFFh; char *
0x180033491  mov     r8, rdi; unsigned int
0x180033494  mov     edx, 1ECh; void *
0x180033499  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003349e  jmp     loc_180033663
0x1800334a3  mov     rcx, [rsi+0C0h]
0x1800334aa  mov     rax, [rcx]
0x1800334ad  mov     rax, [rax+28h]
0x1800334b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334b6  mov     ebx, eax
0x1800334b8  mov     rcx, [rsp+88h]; this
0x1800334c0  lea     rax, aFailedToStopFi_2; "Failed to stop FileIo graphics write ch"...
0x1800334c7  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800334cc  mov     r9d, ebx; char *
0x1800334cf  mov     r8, rdi; unsigned int
0x1800334d2  mov     edx, 1E6h; void *
0x1800334d7  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800334dc  nop
0x1800334dd  mov     rcx, [rsi+0C0h]
0x1800334e4  mov     qword ptr [rsi+0C0h], 0
0x1800334ef  test    rcx, rcx
0x1800334f2  jz      short loc_180033501
0x1800334f4  mov     rax, [rcx]
0x1800334f7  mov     rax, [rax+10h]
0x1800334fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033500  nop
0x180033501  jmp     loc_180033663
0x180033506  mov     rcx, [rsi+0C8h]
0x18003350d  mov     rax, [rcx]
0x180033510  mov     rax, [rax+28h]
0x180033514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033519  mov     ebx, eax
0x18003351b  mov     rcx, [rsp+88h]; this
0x180033523  lea     rax, aFailedToStopFi_1; "Failed to stop FileIo graphics read cha"...
0x18003352a  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003352f  mov     r9d, ebx; char *
0x180033532  mov     r8, rdi; unsigned int
0x180033535  mov     edx, 1DBh; void *
0x18003353a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003353f  nop
0x180033540  mov     rcx, [rsi+0C8h]
0x180033547  mov     qword ptr [rsi+0C8h], 0
0x180033552  test    rcx, rcx
0x180033555  jz      short loc_180033564
0x180033557  mov     rax, [rcx]
0x18003355a  mov     rax, [rax+10h]
0x18003355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033563  nop
0x180033564  jmp     loc_180033663
0x180033569  mov     rax, [rdx]
0x18003356c  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data1
0x180033573  jnz     loc_180033667
0x180033579  mov     rax, [rdx+8]
0x18003357d  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data4
0x180033584  jnz     loc_180033667
0x18003358a  mov     eax, cs:dword_1800C1058
0x180033590  cmp     eax, 4
0x180033593  jbe     short loc_1800335FE
0x180033595  lea     rax, aClosingFileioC; "Closing FileIo cursor channel"
0x18003359c  mov     [rsp+88h+var_30], rax
0x1800335a1  lea     rax, aRdpAvencSinkwr_4; "Rdp::Avenc::SinkWriter::CSinkWriterProc"...
0x1800335a8  mov     [rsp+88h+var_38], rax
0x1800335ad  mov     [rsp+88h+var_48], 1F3h
0x1800335b5  lea     rdi, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800335bc  mov     [rsp+88h+var_40], rdi
0x1800335c1  lea     rax, [rsp+88h+var_30]
0x1800335c6  mov     [rsp+88h+var_50], rax
0x1800335cb  lea     rax, [rsp+88h+var_38]
0x1800335d0  mov     [rsp+88h+var_58], rax
0x1800335d5  lea     rax, [rsp+88h+var_48]
0x1800335da  mov     [rsp+88h+var_60], rax
0x1800335df  lea     rax, [rsp+88h+var_40]
0x1800335e4  mov     qword ptr [rsp+88h+var_68], rax
0x1800335e9  lea     rdx, dword_1800AEDDC
0x1800335f0  lea     rcx, dword_1800C1058
0x1800335f7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800335fc  jmp     short loc_180033605
0x1800335fe  lea     rdi, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180033605  mov     rcx, [rsi+0D0h]
0x18003360c  mov     rax, [rcx]
0x18003360f  mov     rax, [rax+28h]
0x180033613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033618  mov     ebx, eax
0x18003361a  mov     rcx, [rsp+88h]; this
0x180033622  lea     rax, aFailedToStopFi_0; "Failed to stop FileIo cursor channel"
0x180033629  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003362e  mov     r9d, ebx; char *
0x180033631  mov     r8, rdi; unsigned int
0x180033634  mov     edx, 1F9h; void *
0x180033639  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003363e  nop
0x18003363f  mov     rcx, [rsi+0D0h]
0x180033646  mov     qword ptr [rsi+0D0h], 0
0x180033651  test    rcx, rcx
0x180033654  jz      short loc_180033663
0x180033656  mov     rdx, [rcx]
0x180033659  mov     rax, [rdx+10h]
0x18003365d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033662  nop
0x180033663  mov     eax, ebx
0x180033665  jmp     short loc_180033672
0x180033667  mov     eax, 80004005h
0x18003366c  jmp     short loc_180033672
0x18003366e  mov     eax, [rsp+88h+var_48]
0x180033672  add     rsp, 68h
0x180033676  pop     r14
0x180033678  pop     rdi
0x180033679  pop     rsi
0x18003367a  pop     rbx
0x18003367b  retn
```
