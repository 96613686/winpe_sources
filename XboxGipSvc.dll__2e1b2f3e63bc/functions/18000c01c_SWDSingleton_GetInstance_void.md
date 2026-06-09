# SWDSingleton::GetInstance(void)

- ea: `0x18000c01c`
- end: `0x18000c10f`
- name: `?GetInstance@SWDSingleton@@SAPEAV1@XZ`
- size: `243`
- prototype: `struct SWDSingleton *(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002ea0`

## callees

- `0x180002168`
- `0x1800021fc`
- `0x18000231a`
- `0x180002b48`
- `0x18000707c`
- `0x18000c01c`
- `0x18000c118`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c042`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c042`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c09c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c09c`

## pseudocode

```c
struct SWDSingleton *SWDSingleton::GetInstance(void)
{
  SWDSingleton *v0; // rbx
  __int64 v1; // rdx
  __int64 v2; // rcx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+60h] [rbp+8h] BYREF
  SWDSingleton *v6; // [rsp+68h] [rbp+10h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&SWDSingleton::s_singletonCreated, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    v6 = 0;
    try
    {
      v0 = (SWDSingleton *)operator new(8u);
      v6 = v0;
      if ( (int)SWDSingleton::Initialize(v0) < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids);
        }
        std::exception::exception((std::exception *)pExceptionObject);
        throw (std::exception *)pExceptionObject;
      }
      SWDSingleton::s_instance = v0;
      if ( !InitOnceComplete(&SWDSingleton::s_singletonCreated, 0, 0) )
        _std_init_once_link_alternate_names_and_abort(v2, v1);
    }
    catch ( ... )
    {
    }
  }
  return SWDSingleton::s_instance;
}

```

## disassembly

```asm
0x18000c01c  mov     [rsp+arg_10], rbx
0x18000c021  push    rsi
0x18000c022  sub     rsp, 50h
0x18000c026  mov     [rsp+58h+fPending], 0
0x18000c02e  xor     r9d, r9d; lpContext
0x18000c031  lea     r8, [rsp+58h+fPending]; fPending
0x18000c036  xor     edx, edx; dwFlags
0x18000c038  lea     rsi, ?s_singletonCreated@SWDSingleton@@0Uonce_flag@std@@A; std::once_flag SWDSingleton::s_singletonCreated
0x18000c03f  mov     rcx, rsi; lpInitOnce
0x18000c042  call    cs:__imp___std_init_once_begin_initialize
0x18000c048  test    eax, eax
0x18000c04a  jnz     short loc_18000C051
0x18000c04c  lea     ecx, [rax+5]
0x18000c04f  int     29h; Win8: RtlFailFast(ecx)
0x18000c051  cmp     [rsp+58h+fPending], 0
0x18000c056  jz      short loc_18000C0A6
0x18000c058  mov     [rsp+58h+var_38], rsi
0x18000c05d  mov     [rsp+58h+var_30], 4
0x18000c066  mov     [rsp+58h+arg_8], 0
0x18000c06f  mov     ecx, 8; Size
0x18000c074  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c079  mov     rbx, rax
0x18000c07c  mov     [rsp+58h+arg_8], rax
0x18000c081  mov     rcx, rax; this
0x18000c084  call    ?Initialize@SWDSingleton@@AEAAJXZ; SWDSingleton::Initialize(void)
0x18000c089  test    eax, eax
0x18000c08b  js      short loc_18000C0B8
0x18000c08d  mov     cs:?s_instance@SWDSingleton@@0PEAV1@EA, rbx; SWDSingleton * SWDSingleton::s_instance
0x18000c094  xor     r8d, r8d; lpContext
0x18000c097  xor     edx, edx; dwFlags
0x18000c099  mov     rcx, rsi; lpInitOnce
0x18000c09c  call    cs:__imp_InitOnceComplete
0x18000c0a2  test    eax, eax
0x18000c0a4  jz      short loc_18000C108
0x18000c0a6  mov     rax, cs:?s_instance@SWDSingleton@@0PEAV1@EA; SWDSingleton * SWDSingleton::s_instance
0x18000c0ad  mov     rbx, [rsp+58h+arg_10]
0x18000c0b2  add     rsp, 50h
0x18000c0b6  pop     rsi
0x18000c0b7  retn
0x18000c0b8  lea     rax, WPP_GLOBAL_Control
0x18000c0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0c6  cmp     rcx, rax
0x18000c0c9  jz      short loc_18000C0EC
0x18000c0cb  test    byte ptr [rcx+1Ch], 8
0x18000c0cf  jz      short loc_18000C0EC
0x18000c0d1  cmp     byte ptr [rcx+19h], 1
0x18000c0d5  jb      short loc_18000C0EC
0x18000c0d7  mov     edx, 0Ah
0x18000c0dc  lea     r8, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids
0x18000c0e3  mov     rcx, [rcx+10h]
0x18000c0e7  call    WPP_SF_
0x18000c0ec  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000c0f1  call    ??0exception@std@@QEAA@XZ; std::exception::exception(void)
0x18000c0f6  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x18000c0fd  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000c102  call    _CxxThrowException_0
0x18000c108  call    __std_init_once_link_alternate_names_and_abort
```
