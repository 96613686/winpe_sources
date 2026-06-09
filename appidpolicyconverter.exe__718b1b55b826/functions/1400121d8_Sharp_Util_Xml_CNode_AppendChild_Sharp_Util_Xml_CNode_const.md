# Sharp::Util::Xml::CNode::AppendChild(Sharp::Util::Xml::CNode const &)

- ea: `0x1400121d8`
- end: `0x14001226f`
- name: `?AppendChild@CNode@Xml@Util@Sharp@@QEAAXAEBV1234@@Z`
- size: `151`
- prototype: `void __fastcall(Sharp::Util::Xml::CNode *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140012764`

## callees

- `0x140001d1c`
- `0x140007428`
- `0x1400119d4`
- `0x1400121d8`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNode::AppendChild(
        Sharp::Util::Xml::CNode *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  int v2; // ebx
  _BYTE pExceptionObject[64]; // [rsp+20h] [rbp-58h] BYREF

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 168LL))(
         *((_QWORD *)this + 1),
         *((_QWORD *)a2 + 1),
         0);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v2);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v2);
    throw (xml_exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1400121d8  push    rbx
0x1400121da  sub     rsp, 70h
0x1400121de  mov     rax, cs:__security_cookie
0x1400121e5  xor     rax, rsp
0x1400121e8  mov     [rsp+78h+var_18], rax
0x1400121ed  mov     rcx, [rcx+8]
0x1400121f1  xor     r8d, r8d
0x1400121f4  mov     rdx, [rdx+8]
0x1400121f8  mov     rax, [rcx]
0x1400121fb  mov     rax, [rax+0A8h]
0x140012202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012207  mov     ebx, eax
0x140012209  test    eax, eax
0x14001220b  jns     short loc_14001225C
0x14001220d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012214  lea     rax, WPP_GLOBAL_Control
0x14001221b  cmp     rcx, rax
0x14001221e  jz      short loc_14001223E
0x140012220  test    byte ptr [rcx+1Ch], 1
0x140012224  jz      short loc_14001223E
0x140012226  mov     rcx, [rcx+10h]
0x14001222a  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012231  mov     edx, 1Fh
0x140012236  mov     r9d, ebx
0x140012239  call    WPP_SF_d
0x14001223e  mov     edx, ebx; int
0x140012240  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140012245  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x14001224a  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140012251  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140012256  call    _CxxThrowException_0
0x14001225c  mov     rcx, [rsp+78h+var_18]
0x140012261  xor     rcx, rsp; StackCookie
0x140012264  call    __security_check_cookie
0x140012269  add     rsp, 70h
0x14001226d  pop     rbx
0x14001226e  retn
```
