# Broker::BrokerBase::~BrokerBase(void)

- ea: `0x180012dc4`
- end: `0x180012e4c`
- name: `??1BrokerBase@Broker@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018fd0`

## callees

- `0x180004ae0`
- `0x180005b50`
- `0x180012dc4`
- `0x180012e54`
- `0x180012e84`

## pseudocode

```c
void __fastcall Broker::BrokerBase::~BrokerBase(Broker::BrokerBase *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 39);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 37);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 35);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>,0>>::~_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>,0>>((char *)this + 256);
  Broker::BrokeredEventTable::~BrokeredEventTable((Broker::BrokerBase *)((char *)this + 208));
}

```

## disassembly

```asm
0x180012dc4  push    rbx
0x180012dc6  sub     rsp, 20h
0x180012dca  mov     rbx, rcx
0x180012dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dd4  test    dword ptr [rcx+1Ch], 800h
0x180012ddb  jz      short loc_180012DFC
0x180012ddd  cmp     byte ptr [rcx+19h], 5
0x180012de1  jb      short loc_180012DFC
0x180012de3  mov     r9, [rbx+8]
0x180012de7  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180012dee  mov     rcx, [rcx+10h]
0x180012df2  mov     edx, 0Fh
0x180012df7  call    WPP_SF__guid_
0x180012dfc  mov     rcx, [rbx+138h]; this
0x180012e03  test    rcx, rcx
0x180012e06  jz      short loc_180012E0D
0x180012e08  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012e0d  mov     rcx, [rbx+128h]; this
0x180012e14  test    rcx, rcx
0x180012e17  jz      short loc_180012E1E
0x180012e19  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012e1e  mov     rcx, [rbx+118h]; this
0x180012e25  test    rcx, rcx
0x180012e28  jz      short loc_180012E2F
0x180012e2a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012e2f  lea     rcx, [rbx+100h]
0x180012e36  call    ??1?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>,0>>::~_Tree<std::_Tmap_traits<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>,0>>(void)
0x180012e3b  lea     rcx, [rbx+0D0h]; this
0x180012e42  add     rsp, 20h
0x180012e46  pop     rbx
0x180012e47  jmp     ??1BrokeredEventTable@Broker@@QEAA@XZ; Broker::BrokeredEventTable::~BrokeredEventTable(void)
```
