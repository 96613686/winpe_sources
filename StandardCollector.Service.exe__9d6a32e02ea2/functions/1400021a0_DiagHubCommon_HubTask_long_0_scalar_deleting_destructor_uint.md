# DiagHubCommon::HubTask<long,0>::`scalar deleting destructor'(uint)

- ea: `0x1400021a0`
- end: `0x1400021d4`
- name: `??_G?$HubTask@J$0A@@DiagHubCommon@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140002028`
- `0x1400021a0`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall DiagHubCommon::HubTask<long,0>::`scalar deleting destructor'(void *Block, __int64 a2)
{
  char v2; // bl

  v2 = a2;
  DiagHubCommon::HubTask<long,0>::~HubTask<long,0>((__int64)Block, a2);
  if ( (v2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1400021a0  mov     [rsp+arg_0], rbx
0x1400021a5  push    rdi
0x1400021a6  sub     rsp, 20h
0x1400021aa  mov     ebx, edx
0x1400021ac  mov     rdi, rcx
0x1400021af  call    ??1?$HubTask@J$0A@@DiagHubCommon@@UEAA@XZ; DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(void)
0x1400021b4  test    bl, 1
0x1400021b7  jz      short loc_1400021C6
0x1400021b9  mov     edx, 70h ; 'p'
0x1400021be  mov     rcx, rdi; Block
0x1400021c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400021c6  mov     rbx, [rsp+28h+arg_0]
0x1400021cb  mov     rax, rdi
0x1400021ce  add     rsp, 20h
0x1400021d2  pop     rdi
0x1400021d3  retn
```
