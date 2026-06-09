# Sharp::Util::Xml::CNode::GetSpecificChilds(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012c90`
- end: `0x140012d26`
- name: `?GetSpecificChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `150`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140009410`
- `0x140009520`
- `0x1400096c4`
- `0x14000e340`

## callees

- `0x1400070e4`
- `0x140012950`
- `0x140012c90`
- `0x14001377c`
- `0x140013808`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNode::GetSpecificChilds(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD v7[4]; // [rsp+28h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  Sharp::Util::Xml::CNode::GetChilds(a1, v7);
  Sharp::Util::Xml::CNodeCollection::Find((__int64)v7, a2, a3);
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)v7);
  return a2;
}

```

## disassembly

```asm
0x140012c90  mov     rax, rsp
0x140012c93  mov     [rax+8], rbx
0x140012c97  mov     [rax+18h], rsi
0x140012c9b  mov     [rax+10h], rdx
0x140012c9f  push    rdi
0x140012ca0  sub     rsp, 40h
0x140012ca4  mov     rdi, r8
0x140012ca7  mov     rbx, rdx
0x140012caa  mov     rsi, rcx
0x140012cad  mov     dword ptr [rax-28h], 0
0x140012cb4  lea     rax, WPP_GLOBAL_Control
0x140012cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140012cc2  cmp     rcx, rax
0x140012cc5  jz      short loc_140012CE2
0x140012cc7  test    byte ptr [rcx+1Ch], 8
0x140012ccb  jz      short loc_140012CE2
0x140012ccd  mov     edx, 16h
0x140012cd2  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012cd9  mov     rcx, [rcx+10h]
0x140012cdd  call    WPP_SF_
0x140012ce2  lea     rdx, [rsp+48h+var_20]
0x140012ce7  mov     rcx, rsi
0x140012cea  call    ?GetChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@XZ; Sharp::Util::Xml::CNode::GetChilds(void)
0x140012cef  nop
0x140012cf0  mov     r8, rdi
0x140012cf3  mov     rdx, rbx
0x140012cf6  lea     rcx, [rsp+48h+var_20]
0x140012cfb  call    ?Find@CNodeCollection@Xml@Util@Sharp@@QEBA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNodeCollection::Find(std::wstring const &)
0x140012d00  mov     [rsp+48h+var_28], 1
0x140012d08  lea     rcx, [rsp+48h+var_20]; this
0x140012d0d  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x140012d12  mov     rax, rbx
0x140012d15  mov     rbx, [rsp+48h+arg_0]
0x140012d1a  mov     rsi, [rsp+48h+arg_10]
0x140012d1f  add     rsp, 40h
0x140012d23  pop     rdi
0x140012d24  retn
```
