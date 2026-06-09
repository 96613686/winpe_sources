# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vector deleting destructor'(uint)

- ea: `0x180003ee0`
- end: `0x180003f10`
- name: `??_E?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003d38`
- `0x180003ee0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003efc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003efc`

## pseudocode

```c
void *__fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp+arg_0], rbx
0x180003ee5  push    rdi
0x180003ee6  sub     rsp, 20h
0x180003eea  mov     ebx, edx
0x180003eec  mov     rdi, rcx
0x180003eef  call    ??1?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@UEAA@XZ; ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void)
0x180003ef4  test    bl, 1
0x180003ef7  jz      short loc_180003F02
0x180003ef9  mov     rcx, rdi
0x180003efc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003f02  mov     rbx, [rsp+28h+arg_0]
0x180003f07  mov     rax, rdi
0x180003f0a  add     rsp, 20h
0x180003f0e  pop     rdi
0x180003f0f  retn
```
