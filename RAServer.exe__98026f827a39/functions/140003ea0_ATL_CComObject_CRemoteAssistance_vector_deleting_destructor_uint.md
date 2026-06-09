# ATL::CComObject<CRemoteAssistance>::`vector deleting destructor'(uint)

- ea: `0x140003ea0`
- end: `0x140003ed0`
- name: `??_E?$CComObject@VCRemoteAssistance@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CRemoteAssistance *__fastcall(CRemoteAssistance *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000350c`
- `0x140003ea0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003ebc`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ebc`

## pseudocode

```c
CRemoteAssistance *__fastcall ATL::CComObject<CRemoteAssistance>::`vector deleting destructor'(
        CRemoteAssistance *a1,
        char a2)
{
  ATL::CComObject<CRemoteAssistance>::~CComObject<CRemoteAssistance>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003ea0  mov     [rsp+arg_0], rbx
0x140003ea5  push    rdi
0x140003ea6  sub     rsp, 20h
0x140003eaa  mov     ebx, edx
0x140003eac  mov     rdi, rcx
0x140003eaf  call    ??1?$CComObject@VCRemoteAssistance@@@ATL@@UEAA@XZ; ATL::CComObject<CRemoteAssistance>::~CComObject<CRemoteAssistance>(void)
0x140003eb4  test    bl, 1
0x140003eb7  jz      short loc_140003EC2
0x140003eb9  mov     rcx, rdi
0x140003ebc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003ec2  mov     rbx, [rsp+28h+arg_0]
0x140003ec7  mov     rax, rdi
0x140003eca  add     rsp, 20h
0x140003ece  pop     rdi
0x140003ecf  retn
```
