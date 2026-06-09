# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>> * *)

- ea: `0x18000422c`
- end: `0x1800042bf`
- name: `?CreateInstance@?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@SAJPEAPEAV12@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003928`

## callees

- `0x180001730`
- `0x180003bb8`
- `0x18000422c`
- `0x18000aa27`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(
        __int64 *a1)
{
  unsigned int v3; // esi
  void *v4; // rax
  __int64 v5; // r14
  __int64 v6; // rax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  v4 = operator new(0x128u);
  v5 = (__int64)v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x128u);
    v6 = ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(v5);
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
    v3 = 0;
  *a1 = v6;
  return v3;
}

```

## disassembly

```asm
0x18000422c  mov     [rsp+arg_18], rbx
0x180004231  mov     [rsp+arg_0], rcx
0x180004236  push    rsi
0x180004237  push    rdi
0x180004238  push    r14
0x18000423a  sub     rsp, 20h
0x18000423e  mov     rdi, rcx
0x180004241  xor     ebx, ebx
0x180004243  test    rcx, rcx
0x180004246  jnz     short loc_18000424F
0x180004248  mov     eax, 80004003h
0x18000424d  jmp     short loc_1800042B1
0x18000424f  mov     [rcx], rbx
0x180004252  mov     esi, 8007000Eh
0x180004257  mov     [rsp+38h+arg_8], esi
0x18000425b  mov     [rsp+38h+arg_10], rbx
0x180004260  mov     ecx, 128h; Size
0x180004265  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000426a  mov     r14, rax
0x18000426d  test    rax, rax
0x180004270  jz      short loc_18000428C
0x180004272  xor     edx, edx; Val
0x180004274  mov     r8d, 128h; Size
0x18000427a  mov     rcx, rax; void *
0x18000427d  call    memset_0
0x180004282  mov     rcx, r14
0x180004285  call    ??0?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void *)
0x18000428a  jmp     short loc_18000428F
0x18000428c  mov     rax, rbx
0x18000428f  mov     [rsp+38h+arg_10], rax
0x180004294  jmp     short loc_1800042A6
0x180004296  xor     ebx, ebx
0x180004298  mov     rdi, [rsp+38h+arg_0]
0x18000429d  mov     esi, [rsp+38h+arg_8]
0x1800042a1  mov     rax, [rsp+38h+arg_10]
0x1800042a6  test    rax, rax
0x1800042a9  cmovnz  esi, ebx
0x1800042ac  mov     [rdi], rax
0x1800042af  mov     eax, esi
0x1800042b1  mov     rbx, [rsp+38h+arg_18]
0x1800042b6  add     rsp, 20h
0x1800042ba  pop     r14
0x1800042bc  pop     rdi
0x1800042bd  pop     rsi
0x1800042be  retn
```
