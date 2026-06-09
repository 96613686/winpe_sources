# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)

- ea: `0x180013938`
- end: `0x1800139c2`
- name: `??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015120`
- `0x18001bf54`
- `0x18001c978`
- `0x18001dcfc`
- `0x1800204a4`
- `0x18002166c`
- `0x180023f8c`

## callees

- `0x180002f9c`
- `0x180013938`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001395a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001395a`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(__int64 a1, _QWORD *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = RoActivateInstance(a1, &v5);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v5;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v5)(
             v5,
             &GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013938  mov     [rsp+arg_0], rbx
0x18001393d  push    rdi
0x18001393e  sub     rsp, 20h
0x180013942  mov     rdi, rdx
0x180013945  mov     qword ptr [rdx], 0
0x18001394c  lea     rdx, [rsp+28h+arg_8]
0x180013951  mov     [rsp+28h+arg_8], 0
0x18001395a  call    cs:__imp_RoActivateInstance
0x180013960  mov     ebx, eax
0x180013962  test    eax, eax
0x180013964  js      short loc_1800139B5
0x180013966  mov     r8d, 10h; Size
0x18001396c  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180013973  lea     rcx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81; Buf1
0x18001397a  call    memcmp_0
0x18001397f  mov     rcx, [rsp+28h+arg_8]
0x180013984  test    eax, eax
0x180013986  jnz     short loc_18001398D
0x180013988  mov     [rdi], rcx
0x18001398b  jmp     short loc_1800139B5
0x18001398d  mov     rax, [rcx]
0x180013990  lea     rdx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81
0x180013997  mov     r8, rdi
0x18001399a  mov     rax, [rax]
0x18001399d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a2  mov     rcx, [rsp+28h+arg_8]
0x1800139a7  mov     ebx, eax
0x1800139a9  mov     rax, [rcx]
0x1800139ac  mov     rax, [rax+10h]
0x1800139b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139b5  mov     eax, ebx
0x1800139b7  mov     rbx, [rsp+28h+arg_0]
0x1800139bc  add     rsp, 20h
0x1800139c0  pop     rdi
0x1800139c1  retn
```
