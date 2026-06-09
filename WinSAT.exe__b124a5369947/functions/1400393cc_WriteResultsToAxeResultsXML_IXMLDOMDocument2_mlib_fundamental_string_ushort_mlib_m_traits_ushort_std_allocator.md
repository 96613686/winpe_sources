# WriteResultsToAxeResultsXML(IXMLDOMDocument2 *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1400393cc`
- end: `0x140039630`
- name: `?WriteResultsToAxeResultsXML@@YAJPEAUIXMLDOMDocument2@@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x14001a54c`

## callees

- `0x1400039b8`
- `0x140005d78`
- `0x140015c28`
- `0x140016d04`
- `0x14002c424`
- `0x140035398`
- `0x140035a64`
- `0x140035cd8`
- `0x140036700`
- `0x14003808c`
- `0x1400393cc`

## import_xrefs

- `msvcrt!fwprintf` at `0x140039458`
- `msvcrt!fwprintf` at `0x14003947c`
- `msvcrt!fwprintf` at `0x140039520`
- `msvcrt!fwprintf` at `0x14003958f`
- `msvcrt!fwprintf` at `0x1400395ae`
- `msvcrt!fwprintf` at `0x1400395cd`
- `msvcrt!fwprintf` at `0x1400395ec`
- `msvcrt!fwprintf` at `0x140039458`
- `msvcrt!fwprintf` at `0x14003947c`
- `msvcrt!fwprintf` at `0x140039520`
- `msvcrt!fwprintf` at `0x14003958f`
- `msvcrt!fwprintf` at `0x1400395ae`
- `msvcrt!fwprintf` at `0x1400395cd`
- `msvcrt!fwprintf` at `0x1400395ec`
- `msvcrt!fclose` at `0x1400395fb`
- `msvcrt!fclose` at `0x1400395fb`
- `msvcrt!_wfopen_s` at `0x140039435`
- `msvcrt!_wfopen_s` at `0x140039435`

## string_xrefs

- `0x140039413`: `results.xml`
- `0x140039451`: `WriteXML: Error creating results.xml file.\n`
- `0x140039471`: `<?xml version="1.0" encoding="UTF-8" standalone="yes"?>\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WriteResultsToAxeResultsXML(struct IXMLDOMDocument2 *a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rax
  FILE *v6; // rax
  _BYTE v8[8]; // [rsp+30h] [rbp-59h] BYREF
  FILE *v9; // [rsp+38h] [rbp-51h]
  __int64 v10; // [rsp+40h] [rbp-49h]
  __int64 v11; // [rsp+48h] [rbp-41h]
  __int64 v12; // [rsp+50h] [rbp-39h]
  _BYTE v13[8]; // [rsp+58h] [rbp-31h] BYREF
  FILE *v14; // [rsp+60h] [rbp-29h]
  __int64 v15; // [rsp+68h] [rbp-21h]
  __int64 v16; // [rsp+70h] [rbp-19h]
  __int64 v17; // [rsp+78h] [rbp-11h]
  _BYTE v18[8]; // [rsp+80h] [rbp-9h] BYREF
  FILE *v19; // [rsp+88h] [rbp-1h]
  __int64 v20; // [rsp+90h] [rbp+7h]
  __int64 v21; // [rsp+98h] [rbp+Fh]
  __int64 v22; // [rsp+A0h] [rbp+17h]
  _BYTE v23[8]; // [rsp+A8h] [rbp+1Fh] BYREF
  FILE *v24; // [rsp+B0h] [rbp+27h]
  __int64 v25; // [rsp+B8h] [rbp+2Fh]
  __int64 v26; // [rsp+C0h] [rbp+37h]
  __int64 v27; // [rsp+C8h] [rbp+3Fh]
  FILE *Stream; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v29; // [rsp+F8h] [rbp+6Fh]
  char v30; // [rsp+100h] [rbp+77h] BYREF

  v29 = a2;
  Stream = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v30,
    *(_QWORD *)(*(_QWORD *)a2 + 24LL));
  if ( a1 )
  {
    v5 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
           &v30,
           L"results.xml");
    if ( _wfopen_s(&Stream, *(const wchar_t **)(*(_QWORD *)v5 + 24LL), L"w, ccs=UTF-8") )
    {
      v4 = -2147467259;
      v6 = _acrt_iob_func(1u);
      fwprintf(v6, L"WriteXML: Error creating results.xml file.\n");
    }
    else
    {
      v4 = 0;
      if ( App::s_isFormal )
      {
        fwprintf(Stream, L"<?xml version=\"1.0\" encoding=\"UTF-8\" standalone=\"yes\"?>\n");
        CAutoXmlElement::CAutoXmlElement((CAutoXmlElement *)v23, Stream, L"AssessmentResult", &qword_14012B318);
        CAutoXmlElement::CAutoXmlElement((CAutoXmlElement *)v18, Stream, L"Iterations", L"  ");
        CAutoXmlElement::CAutoXmlElement((CAutoXmlElement *)v13, Stream, L"Iteration", L"    ");
        CAutoXmlElement::CAutoXmlElement((CAutoXmlElement *)v8, Stream, L"MetricValues", L"      ");
        v4 = WriteAggregatedResultsToAxeResultsXML(Stream);
        if ( v4 >= 0 )
        {
          v4 = WriteAllD3DAssessmentResultsToAxeResultsXML(a1, Stream);
          if ( v4 >= 0 )
          {
            v4 = WriteDshowEncodeAssessmentResultsToAxeResultsXML(a1, Stream);
            if ( v4 >= 0 )
            {
              WriteAllCPUAssessmentResultsToAxeResultsXML(a1, Stream);
              v4 = WriteMemoryAssessmentResultsToAxeResultsXML(a1, Stream);
            }
          }
        }
        fwprintf(v9, L"%s</%s>%s", v11, v10, v12);
        fwprintf(v14, L"%s</%s>%s", v16, v15, v17);
        fwprintf(v19, L"%s</%s>%s", v21, v20, v22);
        fwprintf(v24, L"%s</%s>%s", v26, v25, v27);
      }
    }
    if ( Stream )
    {
      fclose(Stream);
      Stream = 0;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v30);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(a2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400393cc  mov     [rsp-8+arg_18], rbx
0x1400393d1  mov     [rsp-8+arg_8], rdx
0x1400393d6  push    rbp
0x1400393d7  push    rsi
0x1400393d8  push    rdi
0x1400393d9  lea     rbp, [rsp-47h]
0x1400393de  sub     rsp, 0D0h
0x1400393e5  mov     rsi, rdx
0x1400393e8  mov     rdi, rcx
0x1400393eb  mov     [rbp+57h+Stream], 0
0x1400393f3  mov     rdx, [rdx]
0x1400393f6  mov     rdx, [rdx+18h]
0x1400393fa  lea     rcx, [rbp+57h+arg_10]
0x1400393fe  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140039403  nop
0x140039404  test    rdi, rdi
0x140039407  jnz     short loc_140039413
0x140039409  mov     ebx, 80070057h
0x14003940e  jmp     loc_140039609
0x140039413  lea     rdx, aResultsXml; "results.xml"
0x14003941a  lea     rcx, [rbp+57h+arg_10]
0x14003941e  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x140039423  mov     rdx, [rax]
0x140039426  lea     r8, aWCcsUtf8; "w, ccs=UTF-8"
0x14003942d  mov     rdx, [rdx+18h]; FileName
0x140039431  lea     rcx, [rbp+57h+Stream]; Stream
0x140039435  call    cs:__imp__wfopen_s
0x14003943b  test    eax, eax
0x14003943d  jz      short loc_140039463
0x14003943f  mov     ebx, 80004005h
0x140039444  mov     ecx, 1; Ix
0x140039449  call    __acrt_iob_func
0x14003944e  mov     rcx, rax; Stream
0x140039451  lea     rdx, aWritexmlErrorC; "WriteXML: Error creating results.xml fi"...
0x140039458  call    cs:__imp_fwprintf
0x14003945e  jmp     loc_1400395F2
0x140039463  xor     ebx, ebx
0x140039465  cmp     cs:?s_isFormal@App@@2_NA, bl; bool App::s_isFormal
0x14003946b  jz      loc_1400395F2
0x140039471  lea     rdx, aXmlVersion10En_1; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x140039478  mov     rcx, [rbp+57h+Stream]; Stream
0x14003947c  call    cs:__imp_fwprintf
0x140039482  lea     r9, qword_14012B318; unsigned __int16 *
0x140039489  lea     r8, aAssessmentresu; "AssessmentResult"
0x140039490  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x140039494  lea     rcx, [rbp+57h+var_38]; this
0x140039498  call    ??0CAutoXmlElement@@QEAA@PEAU_iobuf@@PEBG1@Z; CAutoXmlElement::CAutoXmlElement(_iobuf *,ushort const *,ushort const *)
0x14003949d  nop
0x14003949e  lea     r9, asc_14012B4A0; "  "
0x1400394a5  lea     r8, aIterations; "Iterations"
0x1400394ac  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x1400394b0  lea     rcx, [rbp+57h+var_60]; this
0x1400394b4  call    ??0CAutoXmlElement@@QEAA@PEAU_iobuf@@PEBG1@Z; CAutoXmlElement::CAutoXmlElement(_iobuf *,ushort const *,ushort const *)
0x1400394b9  nop
0x1400394ba  lea     r9, asc_140136C68; "    "
0x1400394c1  lea     r8, aIteration; "Iteration"
0x1400394c8  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x1400394cc  lea     rcx, [rbp+57h+var_88]; this
0x1400394d0  call    ??0CAutoXmlElement@@QEAA@PEAU_iobuf@@PEBG1@Z; CAutoXmlElement::CAutoXmlElement(_iobuf *,ushort const *,ushort const *)
0x1400394d5  nop
0x1400394d6  lea     r9, asc_140136C78; "      "
0x1400394dd  lea     r8, aMetricvalues; "MetricValues"
0x1400394e4  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x1400394e8  lea     rcx, [rbp+57h+var_B0]; this
0x1400394ec  call    ??0CAutoXmlElement@@QEAA@PEAU_iobuf@@PEBG1@Z; CAutoXmlElement::CAutoXmlElement(_iobuf *,ushort const *,ushort const *)
0x1400394f1  nop
0x1400394f2  mov     rcx, [rbp+57h+Stream]; Stream
0x1400394f6  call    ?WriteAggregatedResultsToAxeResultsXML@@YAJPEAU_iobuf@@@Z; WriteAggregatedResultsToAxeResultsXML(_iobuf *)
0x1400394fb  mov     ebx, eax
0x1400394fd  test    eax, eax
0x1400394ff  jns     short loc_140039532
0x140039501  mov     rcx, [rbp+57h+var_90]
0x140039505  mov     [rsp+0E0h+var_C0], rcx
0x14003950a  mov     r9, [rbp+57h+var_A0]
0x14003950e  mov     r8, [rbp+57h+var_98]
0x140039512  lea     rdi, aSSS; "%s</%s>%s"
0x140039519  mov     rdx, rdi; Format
0x14003951c  mov     rcx, [rbp+57h+var_A8]; Stream
0x140039520  call    cs:__imp_fwprintf
0x140039526  nop
0x140039527  mov     rcx, [rbp+57h+var_68]
0x14003952b  mov     [rsp+0E0h+var_C0], rcx
0x140039530  jmp     short loc_14003959F
0x140039532  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x140039536  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x140039539  call    ?WriteAllD3DAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMDocument2@@PEAU_iobuf@@@Z; WriteAllD3DAssessmentResultsToAxeResultsXML(IXMLDOMDocument2 *,_iobuf *)
0x14003953e  mov     ebx, eax
0x140039540  test    eax, eax
0x140039542  js      short loc_140039570
0x140039544  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x140039548  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14003954b  call    ?WriteDshowEncodeAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMDocument2@@PEAU_iobuf@@@Z; WriteDshowEncodeAssessmentResultsToAxeResultsXML(IXMLDOMDocument2 *,_iobuf *)
0x140039550  mov     ebx, eax
0x140039552  test    eax, eax
0x140039554  js      short loc_140039570
0x140039556  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x14003955a  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14003955d  call    ?WriteAllCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMDocument2@@PEAU_iobuf@@@Z; WriteAllCPUAssessmentResultsToAxeResultsXML(IXMLDOMDocument2 *,_iobuf *)
0x140039562  mov     rdx, [rbp+57h+Stream]; struct _iobuf *
0x140039566  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x140039569  call    ?WriteMemoryAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMDocument2@@PEAU_iobuf@@@Z; WriteMemoryAssessmentResultsToAxeResultsXML(IXMLDOMDocument2 *,_iobuf *)
0x14003956e  mov     ebx, eax
0x140039570  mov     rax, [rbp+57h+var_90]
0x140039574  mov     r9, [rbp+57h+var_A0]
0x140039578  mov     [rsp+0E0h+var_C0], rax
0x14003957d  lea     rdi, aSSS; "%s</%s>%s"
0x140039584  mov     r8, [rbp+57h+var_98]
0x140039588  mov     rdx, rdi; Format
0x14003958b  mov     rcx, [rbp+57h+var_A8]; Stream
0x14003958f  call    cs:__imp_fwprintf
0x140039595  nop
0x140039596  mov     rax, [rbp+57h+var_68]
0x14003959a  mov     [rsp+0E0h+var_C0], rax
0x14003959f  mov     r9, [rbp+57h+var_78]
0x1400395a3  mov     r8, [rbp+57h+var_70]
0x1400395a7  mov     rdx, rdi; Format
0x1400395aa  mov     rcx, [rbp+57h+var_80]; Stream
0x1400395ae  call    cs:__imp_fwprintf
0x1400395b4  nop
0x1400395b5  mov     rax, [rbp+57h+var_40]
0x1400395b9  mov     [rsp+0E0h+var_C0], rax
0x1400395be  mov     r9, [rbp+57h+var_50]
0x1400395c2  mov     r8, [rbp+57h+var_48]
0x1400395c6  mov     rdx, rdi; Format
0x1400395c9  mov     rcx, [rbp+57h+var_58]; Stream
0x1400395cd  call    cs:__imp_fwprintf
0x1400395d3  nop
0x1400395d4  mov     rax, [rbp+57h+var_18]
0x1400395d8  mov     [rsp+0E0h+var_C0], rax
0x1400395dd  mov     r9, [rbp+57h+var_28]
0x1400395e1  mov     r8, [rbp+57h+var_20]
0x1400395e5  mov     rdx, rdi; Format
0x1400395e8  mov     rcx, [rbp+57h+var_30]; Stream
0x1400395ec  call    cs:__imp_fwprintf
0x1400395f2  mov     rcx, [rbp+57h+Stream]; Stream
0x1400395f6  test    rcx, rcx
0x1400395f9  jz      short loc_140039609
0x1400395fb  call    cs:__imp_fclose
0x140039601  mov     [rbp+57h+Stream], 0
0x140039609  lea     rcx, [rbp+57h+arg_10]
0x14003960d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140039612  nop
0x140039613  mov     rcx, rsi
0x140039616  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003961b  mov     eax, ebx
0x14003961d  mov     rbx, [rsp+0E0h+arg_18]
0x140039625  add     rsp, 0D0h
0x14003962c  pop     rdi
0x14003962d  pop     rsi
0x14003962e  pop     rbp
0x14003962f  retn
```
