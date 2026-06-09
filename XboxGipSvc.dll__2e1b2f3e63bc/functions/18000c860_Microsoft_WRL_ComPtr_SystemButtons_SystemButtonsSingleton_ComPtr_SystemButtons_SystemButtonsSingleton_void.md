# Microsoft::WRL::ComPtr<SystemButtons::SystemButtonsSingleton>::~ComPtr<SystemButtons::SystemButtonsSingleton>(void)

- ea: `0x18000c860`
- end: `0x18000c880`
- name: `??1?$ComPtr@VSystemButtonsSingleton@SystemButtons@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `int __fastcall(SystemButtons::SystemButtonsSingleton **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011793`

## callees

- `0x18000c860`
- `0x18000d970`

## pseudocode

```c
int __fastcall Microsoft::WRL::ComPtr<SystemButtons::SystemButtonsSingleton>::~ComPtr<SystemButtons::SystemButtonsSingleton>(
        SystemButtons::SystemButtonsSingleton **a1)
{
  SystemButtons::SystemButtonsSingleton *v1; // rax

  v1 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    LODWORD(v1) = SystemButtons::SystemButtonsSingleton::Release(v1);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000c860  sub     rsp, 28h
0x18000c864  mov     rax, [rcx]
0x18000c867  test    rax, rax
0x18000c86a  jz      short loc_18000C87B
0x18000c86c  mov     qword ptr [rcx], 0
0x18000c873  mov     rcx, rax; this
0x18000c876  call    ?Release@SystemButtonsSingleton@SystemButtons@@UEAAKXZ; SystemButtons::SystemButtonsSingleton::Release(void)
0x18000c87b  add     rsp, 28h
0x18000c87f  retn
```
