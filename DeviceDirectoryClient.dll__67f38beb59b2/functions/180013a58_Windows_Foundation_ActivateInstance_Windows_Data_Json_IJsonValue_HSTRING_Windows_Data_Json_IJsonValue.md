# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)

- ea: `0x180013a58`
- end: `0x180013ae2`
- name: `??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015fbc`
- `0x180016aa4`
- `0x1800183c4`
- `0x180022240`
- `0x180023180`
- `0x180027dc8`

## callees

- `0x180002f9c`
- `0x180013a58`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013a7a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013a7a`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(__int64 a1, _QWORD *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = RoActivateInstance(a1, &v5);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v5;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v5)(
             v5,
             &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013a58  mov     [rsp+arg_0], rbx
0x180013a5d  push    rdi
0x180013a5e  sub     rsp, 20h
0x180013a62  mov     rdi, rdx
0x180013a65  mov     qword ptr [rdx], 0
0x180013a6c  lea     rdx, [rsp+28h+arg_8]
0x180013a71  mov     [rsp+28h+arg_8], 0
0x180013a7a  call    cs:__imp_RoActivateInstance
0x180013a80  mov     ebx, eax
0x180013a82  test    eax, eax
0x180013a84  js      short loc_180013AD5
0x180013a86  mov     r8d, 10h; Size
0x180013a8c  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180013a93  lea     rcx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e; Buf1
0x180013a9a  call    memcmp_0
0x180013a9f  mov     rcx, [rsp+28h+arg_8]
0x180013aa4  test    eax, eax
0x180013aa6  jnz     short loc_180013AAD
0x180013aa8  mov     [rdi], rcx
0x180013aab  jmp     short loc_180013AD5
0x180013aad  mov     rax, [rcx]
0x180013ab0  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180013ab7  mov     r8, rdi
0x180013aba  mov     rax, [rax]
0x180013abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac2  mov     rcx, [rsp+28h+arg_8]
0x180013ac7  mov     ebx, eax
0x180013ac9  mov     rax, [rcx]
0x180013acc  mov     rax, [rax+10h]
0x180013ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ad5  mov     eax, ebx
0x180013ad7  mov     rbx, [rsp+28h+arg_0]
0x180013adc  add     rsp, 20h
0x180013ae0  pop     rdi
0x180013ae1  retn
```
