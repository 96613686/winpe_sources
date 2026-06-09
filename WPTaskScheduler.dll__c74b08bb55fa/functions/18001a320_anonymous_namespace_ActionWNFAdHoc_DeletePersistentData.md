# _anonymous_namespace_::ActionWNFAdHoc::DeletePersistentData

- ea: `0x18001a320`
- end: `0x18001a36f`
- name: `_anonymous_namespace_::ActionWNFAdHoc::DeletePersistentData`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18001a320`
- `0x180020a64`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18001a343`
- `ntdll!NtDeleteWnfStateName` at `0x18001a343`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionWNFAdHoc::DeletePersistentData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v5; // ecx
  int v6; // eax

  v5 = 0;
  if ( *(_QWORD *)(a1 + 160) )
  {
    v6 = NtDeleteWnfStateName(a1 + 160, a2, a3, a4);
    v5 = HRESULTFromNTSTATUS(v6);
    *(_DWORD *)(a1 + 160) = 0;
    *(_DWORD *)(a1 + 164) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001a320  mov     [rsp+arg_0], rbx
0x18001a325  push    rdi
0x18001a326  sub     rsp, 20h
0x18001a32a  mov     rbx, rcx
0x18001a32d  xor     ecx, ecx
0x18001a32f  lea     rdi, [rbx+0A0h]
0x18001a336  mov     eax, [rdi]
0x18001a338  or      eax, [rbx+0A4h]
0x18001a33e  jz      short loc_18001A362
0x18001a340  mov     rcx, rdi
0x18001a343  call    cs:__imp_NtDeleteWnfStateName
0x18001a349  mov     ecx, eax; int
0x18001a34b  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x18001a350  mov     ecx, eax
0x18001a352  mov     dword ptr [rdi], 0
0x18001a358  mov     dword ptr [rbx+0A4h], 0
0x18001a362  mov     rbx, [rsp+28h+arg_0]
0x18001a367  mov     eax, ecx
0x18001a369  add     rsp, 20h
0x18001a36d  pop     rdi
0x18001a36e  retn
```
