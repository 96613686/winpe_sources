# Sharp::Util::Xml::CDocument::CDocument(void)

- ea: `0x1400118bc`
- end: `0x14001196d`
- name: `??0CDocument@Xml@Util@Sharp@@QEAA@XZ`
- size: `177`
- prototype: `Sharp::Util::Xml::CDocument *__fastcall(Sharp::Util::Xml::CDocument *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a9ac`

## callees

- `0x1400070e4`
- `0x1400117c4`
- `0x1400118bc`
- `0x140011a6c`
- `0x140011be8`

## pseudocode

```c
Sharp::Util::Xml::CDocument *__fastcall Sharp::Util::Xml::CDocument::CDocument(Sharp::Util::Xml::CDocument *this)
{
  struct IUnknown **v2; // rdi
  struct IUnknown *v4; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = &Sharp::Util::Xml::CDocument::`vftable';
  v2 = (struct IUnknown **)((char *)this + 8);
  v4 = (struct IUnknown *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids);
  Sharp::Util::ComHelper::CoCreateInstance<IXMLDOMDocument2>((LPVOID *)&v4);
  if ( *v2 != v4 )
    ATL::AtlComPtrAssign(v2, v4);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v4);
  return this;
}

```

## disassembly

```asm
0x1400118bc  mov     rax, rsp
0x1400118bf  mov     [rax+18h], rbx
0x1400118c3  mov     [rax+20h], rsi
0x1400118c7  mov     [rax+8], rcx
0x1400118cb  push    rdi
0x1400118cc  sub     rsp, 40h
0x1400118d0  mov     rsi, rcx
0x1400118d3  mov     dword ptr [rax-18h], 0
0x1400118da  lea     rax, ??_7CDocument@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CDocument::`vftable'
0x1400118e1  mov     [rcx], rax
0x1400118e4  lea     rdi, [rcx+8]
0x1400118e8  mov     [rsp+48h+arg_8], rdi
0x1400118ed  mov     qword ptr [rdi], 0
0x1400118f4  lea     rax, WPP_GLOBAL_Control
0x1400118fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011902  cmp     rcx, rax
0x140011905  jz      short loc_140011923
0x140011907  test    byte ptr [rcx+1Ch], 8
0x14001190b  jz      short loc_140011923
0x14001190d  mov     edx, 0Ah
0x140011912  lea     r8, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids
0x140011919  mov     rcx, [rcx+10h]
0x14001191d  call    WPP_SF_
0x140011922  nop
0x140011923  lea     rcx, [rsp+48h+arg_8]; ppv
0x140011928  call    ??$CoCreateInstance@UIXMLDOMDocument2@@@ComHelper@Util@Sharp@@YA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBU_GUID@@0KPEAUIUnknown@@@Z; Sharp::Util::ComHelper::CoCreateInstance<IXMLDOMDocument2>(_GUID const &,_GUID const &,ulong,IUnknown *)
0x14001192d  mov     ebx, 1
0x140011932  mov     [rsp+48h+var_18], ebx
0x140011936  mov     rdx, [rsp+48h+arg_8]; struct IUnknown *
0x14001193b  cmp     [rdi], rdx
0x14001193e  jz      short loc_140011948
0x140011940  mov     rcx, rdi; struct IUnknown **
0x140011943  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140011948  and     ebx, 0FFFFFFFEh
0x14001194b  mov     [rsp+48h+var_18], ebx
0x14001194f  lea     rcx, [rsp+48h+arg_8]
0x140011954  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140011959  nop
0x14001195a  mov     rax, rsi
0x14001195d  mov     rbx, [rsp+48h+arg_10]
0x140011962  mov     rsi, [rsp+48h+arg_18]
0x140011967  add     rsp, 40h
0x14001196b  pop     rdi
0x14001196c  retn
```
