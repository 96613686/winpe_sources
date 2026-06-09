# CWMIBroker::GetNamespace(WString const &,IWbemServices * *)

- ea: `0x140003320`
- end: `0x140003358`
- name: `?GetNamespace@CWMIBroker@@SAJAEBVWString@@PEAPEAUIWbemServices@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(const struct WString *, struct IWbemServices **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004e24`

## callees

- `0x140002e44`
- `0x140002f04`
- `0x14000304c`

## pseudocode

```c
__int64 __fastcall CWMIBroker::GetNamespace(const struct WString *a1, struct IWbemServices **a2)
{
  unsigned __int16 *v4[3]; // [rsp+20h] [rbp-18h] BYREF

  CWMIBroker::CWMIBroker((CWMIBroker *)v4, a1);
  LODWORD(a2) = CWMIBroker::Connect((const OLECHAR **)v4, a2);
  CWMIBroker::~CWMIBroker(v4);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x140003320  push    rbx
0x140003322  sub     rsp, 30h
0x140003326  mov     rbx, rdx
0x140003329  mov     rdx, rcx; struct WString *
0x14000332c  lea     rcx, [rsp+38h+var_18]; this
0x140003331  call    ??0CWMIBroker@@QEAA@AEBVWString@@@Z; CWMIBroker::CWMIBroker(WString const &)
0x140003336  nop
0x140003337  mov     rdx, rbx; struct IWbemServices **
0x14000333a  lea     rcx, [rsp+38h+var_18]; this
0x14000333f  call    ?Connect@CWMIBroker@@AEAAJPEAPEAUIWbemServices@@@Z; CWMIBroker::Connect(IWbemServices * *)
0x140003344  mov     ebx, eax
0x140003346  lea     rcx, [rsp+38h+var_18]; this
0x14000334b  call    ??1CWMIBroker@@UEAA@XZ; CWMIBroker::~CWMIBroker(void)
0x140003350  mov     eax, ebx
0x140003352  add     rsp, 30h
0x140003356  pop     rbx
0x140003357  retn
```
