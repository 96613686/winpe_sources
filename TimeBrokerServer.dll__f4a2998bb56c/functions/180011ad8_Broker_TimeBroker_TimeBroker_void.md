# Broker::TimeBroker::~TimeBroker(void)

- ea: `0x180011ad8`
- end: `0x180011baf`
- name: `??1TimeBroker@Broker@@QEAA@XZ`
- size: `215`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016590`

## callees

- `0x180005b30`
- `0x180011ad8`
- `0x180011bb8`
- `0x180011be8`
- `0x18001321c`

## pseudocode

```c
void __fastcall Broker::TimeBroker::~TimeBroker(Broker::TimeBroker *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  std::shared_ptr<Broker::SystemTimer>::reset((char *)this + 80);
  std::shared_ptr<Broker::SystemTimer>::reset((char *)this + 96);
  *((_QWORD *)this + 16) = 0;
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  std::shared_ptr<Broker::SystemTimer>::reset((char *)this + 112);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 19);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 17);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 15);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  `eh vector destructor iterator'(
    (char *)this + 80,
    0x10u,
    2u,
    (void (*)(void *))std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>);
  std::_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>::~_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>((void **)this + 8);
  `eh vector destructor iterator'((char *)this + 32, 0x10u, 2u, (void (*)(void *))Broker::TimerWheel::~TimerWheel);
  `eh vector destructor iterator'(this, 0x10u, 2u, (void (*)(void *))Broker::TimerWheel::~TimerWheel);
}

```

## disassembly

```asm
0x180011ad8  push    rbx
0x180011ada  push    rbp
0x180011adb  push    rsi
0x180011adc  push    rdi
0x180011add  sub     rsp, 28h
0x180011ae1  mov     rbx, rcx
0x180011ae4  add     rcx, 50h ; 'P'
0x180011ae8  call    ?reset@?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::SystemTimer>::reset(void)
0x180011aed  lea     rcx, [rbx+60h]
0x180011af1  call    ?reset@?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::SystemTimer>::reset(void)
0x180011af6  mov     qword ptr [rbx+80h], 0
0x180011b01  mov     rcx, [rbx+88h]; this
0x180011b08  mov     qword ptr [rbx+88h], 0
0x180011b13  test    rcx, rcx
0x180011b16  jz      short loc_180011B1D
0x180011b18  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011b1d  lea     rcx, [rbx+70h]
0x180011b21  call    ?reset@?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::SystemTimer>::reset(void)
0x180011b26  mov     rcx, [rbx+98h]; this
0x180011b2d  test    rcx, rcx
0x180011b30  jz      short loc_180011B37
0x180011b32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011b37  mov     rcx, [rbx+88h]; this
0x180011b3e  test    rcx, rcx
0x180011b41  jz      short loc_180011B48
0x180011b43  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011b48  mov     rcx, [rbx+78h]; this
0x180011b4c  test    rcx, rcx
0x180011b4f  jz      short loc_180011B56
0x180011b51  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011b56  lea     r9, ??1?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@QEAA@XZ; void (*)(void *)
0x180011b5d  mov     ebp, 2
0x180011b62  mov     r8d, ebp; unsigned __int64
0x180011b65  lea     esi, [rbp+0Eh]
0x180011b68  mov     edx, esi; unsigned __int64
0x180011b6a  lea     rcx, [rbx+50h]; void *
0x180011b6e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011b73  lea     rcx, [rbx+40h]
0x180011b77  call    ??1?$_Tree@V?$_Tmap_traits@_JV?$shared_ptr@VTimeEvent@Broker@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@2@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>::~_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>(void)
0x180011b7c  lea     rcx, [rbx+20h]; void *
0x180011b80  lea     r9, ??1TimerWheel@Broker@@QEAA@XZ; void (*)(void *)
0x180011b87  mov     r8d, ebp; unsigned __int64
0x180011b8a  mov     edx, esi; unsigned __int64
0x180011b8c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011b91  lea     r9, ??1TimerWheel@Broker@@QEAA@XZ; void (*)(void *)
0x180011b98  mov     r8d, ebp; unsigned __int64
0x180011b9b  mov     edx, esi; unsigned __int64
0x180011b9d  mov     rcx, rbx; void *
0x180011ba0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011ba5  nop
0x180011ba6  add     rsp, 28h
0x180011baa  pop     rdi
0x180011bab  pop     rsi
0x180011bac  pop     rbp
0x180011bad  pop     rbx
0x180011bae  retn
```
