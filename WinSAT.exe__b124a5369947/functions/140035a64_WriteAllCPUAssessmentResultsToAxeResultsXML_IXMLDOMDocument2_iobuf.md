# WriteAllCPUAssessmentResultsToAxeResultsXML(IXMLDOMDocument2 *,_iobuf *)

- ea: `0x140035a64`
- end: `0x140035cd0`
- name: `?WriteAllCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMDocument2@@PEAU_iobuf@@@Z`
- size: `620`
- prototype: `int(struct IXMLDOMDocument2 *, struct _iobuf *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400393cc`

## callees

- `0x140005f10`
- `0x14000712c`
- `0x140016d04`
- `0x140035a64`
- `0x140037544`
- `0x1400558e4`

## string_xrefs

- `0x140035aaa`: `/WinSAT/CPUEncryptionAssessment[MaxThreads='1']`
- `0x140035aec`: `/WinSAT/CPUEncryptionAssessment[MaxThreads='NumberOfSchedulableUnits']`
- `0x140035b2e`: `/WinSAT/CPUCompressionAssessment[MaxThreads='1']`
- `0x140035b4d`: `CompOne`
- `0x140035b70`: `/WinSAT/CPUCompressionAssessment[MaxThreads='NumberOfSchedulableUnits']`
- `0x140035b8f`: `CompMulti`
- `0x140035bb2`: `/WinSAT/CPUEncryption2Assessment[MaxThreads='1']`
- `0x140035bf4`: `/WinSAT/CPUEncryption2Assessment[MaxThreads='NumberOfSchedulableUnits']`
- `0x140035c36`: `/WinSAT/CPUCompression2Assessment[MaxThreads='1']`
- `0x140035c55`: `CompOne2`
- `0x140035c74`: `/WinSAT/CPUCompression2Assessment[MaxThreads='NumberOfSchedulableUnits']`
- `0x140035c93`: `CompMulti2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteAllCPUAssessmentResultsToAxeResultsXML(struct IXMLDOMDocument2 *a1, struct _iobuf *a2)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // ebx
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  struct IXMLDOMNode *v14; // [rsp+50h] [rbp+20h] BYREF
  char v15; // [rsp+60h] [rbp+30h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v15);
  v14 = 0;
  if ( a1 && a2 )
  {
    if ( (int)mlib::XmlDOM::SelectSingleNode(
                (_DWORD)a1,
                (unsigned int)L"/WinSAT/CPUEncryptionAssessment[MaxThreads='1']",
                v4,
                (unsigned int)&v14,
                (__int64)&v15) < 0
      || !v14
      || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"EnOne", a2), v6 >= 0) )
    {
      if ( (int)mlib::XmlDOM::SelectSingleNode(
                  (_DWORD)a1,
                  (unsigned int)L"/WinSAT/CPUEncryptionAssessment[MaxThreads='NumberOfSchedulableUnits']",
                  v5,
                  (unsigned int)&v14,
                  (__int64)&v15) < 0
        || !v14
        || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"EnMulti", a2), v6 >= 0) )
      {
        if ( (int)mlib::XmlDOM::SelectSingleNode(
                    (_DWORD)a1,
                    (unsigned int)L"/WinSAT/CPUCompressionAssessment[MaxThreads='1']",
                    v7,
                    (unsigned int)&v14,
                    (__int64)&v15) < 0
          || !v14
          || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"CompOne", a2), v6 >= 0) )
        {
          if ( (int)mlib::XmlDOM::SelectSingleNode(
                      (_DWORD)a1,
                      (unsigned int)L"/WinSAT/CPUCompressionAssessment[MaxThreads='NumberOfSchedulableUnits']",
                      v8,
                      (unsigned int)&v14,
                      (__int64)&v15) < 0
            || !v14
            || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"CompMulti", a2), v6 >= 0) )
          {
            if ( (int)mlib::XmlDOM::SelectSingleNode(
                        (_DWORD)a1,
                        (unsigned int)L"/WinSAT/CPUEncryption2Assessment[MaxThreads='1']",
                        v9,
                        (unsigned int)&v14,
                        (__int64)&v15) < 0
              || !v14
              || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"EnOne2", a2), v6 >= 0) )
            {
              if ( (int)mlib::XmlDOM::SelectSingleNode(
                          (_DWORD)a1,
                          (unsigned int)L"/WinSAT/CPUEncryption2Assessment[MaxThreads='NumberOfSchedulableUnits']",
                          v10,
                          (unsigned int)&v14,
                          (__int64)&v15) < 0
                || !v14
                || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"EnMulti2", a2), v6 >= 0) )
              {
                if ( (int)mlib::XmlDOM::SelectSingleNode(
                            (_DWORD)a1,
                            (unsigned int)L"/WinSAT/CPUCompression2Assessment[MaxThreads='1']",
                            v11,
                            (unsigned int)&v14,
                            (__int64)&v15) < 0
                  || !v14
                  || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"CompOne2", a2), v6 >= 0) )
                {
                  if ( (int)mlib::XmlDOM::SelectSingleNode(
                              (_DWORD)a1,
                              (unsigned int)L"/WinSAT/CPUCompression2Assessment[MaxThreads='NumberOfSchedulableUnits']",
                              v12,
                              (unsigned int)&v14,
                              (__int64)&v15) < 0
                    || !v14
                    || (v6 = WriteIndividualCPUAssessmentResultsToAxeResultsXML(v14, L"CompMulti2", a2), v6 >= 0) )
                  {
                    v6 = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v14);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140035a64  mov     [rsp-18h+arg_8], rbx
0x140035a69  push    rbp
0x140035a6a  push    rsi
0x140035a6b  push    rdi
0x140035a6c  mov     rbp, rsp
0x140035a6f  sub     rsp, 30h
0x140035a73  mov     rdi, rdx
0x140035a76  mov     rsi, rcx
0x140035a79  lea     rcx, [rbp+arg_10]
0x140035a7d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140035a82  nop
0x140035a83  mov     [rbp+arg_0], 0
0x140035a8b  test    rsi, rsi
0x140035a8e  jz      loc_140035CA9
0x140035a94  test    rdi, rdi
0x140035a97  jz      loc_140035CA9
0x140035a9d  lea     rax, [rbp+arg_10]
0x140035aa1  mov     [rsp+30h+var_10], rax
0x140035aa6  lea     r9, [rbp+arg_0]
0x140035aaa  lea     rdx, aWinsatCpuencry_4; "/WinSAT/CPUEncryptionAssessment[MaxThre"...
0x140035ab1  mov     rcx, rsi
0x140035ab4  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035ab9  test    eax, eax
0x140035abb  js      short loc_140035ADF
0x140035abd  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035ac1  test    rcx, rcx
0x140035ac4  jz      short loc_140035ADF
0x140035ac6  mov     r8, rdi; struct _iobuf *
0x140035ac9  lea     rdx, aEnone; "EnOne"
0x140035ad0  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035ad5  mov     ebx, eax
0x140035ad7  test    eax, eax
0x140035ad9  js      loc_140035CAE
0x140035adf  lea     rax, [rbp+arg_10]
0x140035ae3  mov     [rsp+30h+var_10], rax
0x140035ae8  lea     r9, [rbp+arg_0]
0x140035aec  lea     rdx, aWinsatCpuencry_3; "/WinSAT/CPUEncryptionAssessment[MaxThre"...
0x140035af3  mov     rcx, rsi
0x140035af6  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035afb  test    eax, eax
0x140035afd  js      short loc_140035B21
0x140035aff  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035b03  test    rcx, rcx
0x140035b06  jz      short loc_140035B21
0x140035b08  mov     r8, rdi; struct _iobuf *
0x140035b0b  lea     rdx, aEnmulti; "EnMulti"
0x140035b12  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035b17  mov     ebx, eax
0x140035b19  test    eax, eax
0x140035b1b  js      loc_140035CAE
0x140035b21  lea     rax, [rbp+arg_10]
0x140035b25  mov     [rsp+30h+var_10], rax
0x140035b2a  lea     r9, [rbp+arg_0]
0x140035b2e  lea     rdx, aWinsatCpucompr_6; "/WinSAT/CPUCompressionAssessment[MaxThr"...
0x140035b35  mov     rcx, rsi
0x140035b38  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035b3d  test    eax, eax
0x140035b3f  js      short loc_140035B63
0x140035b41  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035b45  test    rcx, rcx
0x140035b48  jz      short loc_140035B63
0x140035b4a  mov     r8, rdi; struct _iobuf *
0x140035b4d  lea     rdx, aCompone; "CompOne"
0x140035b54  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035b59  mov     ebx, eax
0x140035b5b  test    eax, eax
0x140035b5d  js      loc_140035CAE
0x140035b63  lea     rax, [rbp+arg_10]
0x140035b67  mov     [rsp+30h+var_10], rax
0x140035b6c  lea     r9, [rbp+arg_0]
0x140035b70  lea     rdx, aWinsatCpucompr_5; "/WinSAT/CPUCompressionAssessment[MaxThr"...
0x140035b77  mov     rcx, rsi
0x140035b7a  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035b7f  test    eax, eax
0x140035b81  js      short loc_140035BA5
0x140035b83  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035b87  test    rcx, rcx
0x140035b8a  jz      short loc_140035BA5
0x140035b8c  mov     r8, rdi; struct _iobuf *
0x140035b8f  lea     rdx, aCompmulti; "CompMulti"
0x140035b96  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035b9b  mov     ebx, eax
0x140035b9d  test    eax, eax
0x140035b9f  js      loc_140035CAE
0x140035ba5  lea     rax, [rbp+arg_10]
0x140035ba9  mov     [rsp+30h+var_10], rax
0x140035bae  lea     r9, [rbp+arg_0]
0x140035bb2  lea     rdx, aWinsatCpuencry_1; "/WinSAT/CPUEncryption2Assessment[MaxThr"...
0x140035bb9  mov     rcx, rsi
0x140035bbc  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035bc1  test    eax, eax
0x140035bc3  js      short loc_140035BE7
0x140035bc5  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035bc9  test    rcx, rcx
0x140035bcc  jz      short loc_140035BE7
0x140035bce  mov     r8, rdi; struct _iobuf *
0x140035bd1  lea     rdx, aEnone2; "EnOne2"
0x140035bd8  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035bdd  mov     ebx, eax
0x140035bdf  test    eax, eax
0x140035be1  js      loc_140035CAE
0x140035be7  lea     rax, [rbp+arg_10]
0x140035beb  mov     [rsp+30h+var_10], rax
0x140035bf0  lea     r9, [rbp+arg_0]
0x140035bf4  lea     rdx, aWinsatCpuencry_0; "/WinSAT/CPUEncryption2Assessment[MaxThr"...
0x140035bfb  mov     rcx, rsi
0x140035bfe  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035c03  test    eax, eax
0x140035c05  js      short loc_140035C29
0x140035c07  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035c0b  test    rcx, rcx
0x140035c0e  jz      short loc_140035C29
0x140035c10  mov     r8, rdi; struct _iobuf *
0x140035c13  lea     rdx, aEnmulti2; "EnMulti2"
0x140035c1a  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035c1f  mov     ebx, eax
0x140035c21  test    eax, eax
0x140035c23  js      loc_140035CAE
0x140035c29  lea     rax, [rbp+arg_10]
0x140035c2d  mov     [rsp+30h+var_10], rax
0x140035c32  lea     r9, [rbp+arg_0]
0x140035c36  lea     rdx, aWinsatCpucompr_0; "/WinSAT/CPUCompression2Assessment[MaxTh"...
0x140035c3d  mov     rcx, rsi
0x140035c40  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035c45  test    eax, eax
0x140035c47  js      short loc_140035C67
0x140035c49  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035c4d  test    rcx, rcx
0x140035c50  jz      short loc_140035C67
0x140035c52  mov     r8, rdi; struct _iobuf *
0x140035c55  lea     rdx, aCompone2; "CompOne2"
0x140035c5c  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035c61  mov     ebx, eax
0x140035c63  test    eax, eax
0x140035c65  js      short loc_140035CAE
0x140035c67  lea     rax, [rbp+arg_10]
0x140035c6b  mov     [rsp+30h+var_10], rax
0x140035c70  lea     r9, [rbp+arg_0]
0x140035c74  lea     rdx, aWinsatCpucompr; "/WinSAT/CPUCompression2Assessment[MaxTh"...
0x140035c7b  mov     rcx, rsi
0x140035c7e  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140035c83  test    eax, eax
0x140035c85  js      short loc_140035CA5
0x140035c87  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x140035c8b  test    rcx, rcx
0x140035c8e  jz      short loc_140035CA5
0x140035c90  mov     r8, rdi; struct _iobuf *
0x140035c93  lea     rdx, aCompmulti2; "CompMulti2"
0x140035c9a  call    ?WriteIndividualCPUAssessmentResultsToAxeResultsXML@@YAJPEAUIXMLDOMNode@@PEBGPEAU_iobuf@@@Z; WriteIndividualCPUAssessmentResultsToAxeResultsXML(IXMLDOMNode *,ushort const *,_iobuf *)
0x140035c9f  mov     ebx, eax
0x140035ca1  test    eax, eax
0x140035ca3  js      short loc_140035CAE
0x140035ca5  xor     ebx, ebx
0x140035ca7  jmp     short loc_140035CAE
0x140035ca9  mov     ebx, 80070057h
0x140035cae  lea     rcx, [rbp+arg_0]
0x140035cb2  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140035cb7  nop
0x140035cb8  lea     rcx, [rbp+arg_10]
0x140035cbc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140035cc1  mov     eax, ebx
0x140035cc3  mov     rbx, [rsp+30h+arg_8]
0x140035cc8  add     rsp, 30h
0x140035ccc  pop     rdi
0x140035ccd  pop     rsi
0x140035cce  pop     rbp
0x140035ccf  retn
```
