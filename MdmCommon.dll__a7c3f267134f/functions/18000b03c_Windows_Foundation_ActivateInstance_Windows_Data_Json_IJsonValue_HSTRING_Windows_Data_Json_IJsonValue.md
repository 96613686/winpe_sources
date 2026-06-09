# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000b03c`
- end: `0x18000b0cd`
- name: `??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bd94`
- `0x18000f3b8`

## callees

- `0x18000b03c`
- `0x18001dbe4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000b05e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000b05e`

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
0x18000b03c  mov     [rsp+arg_0], rbx
0x18000b041  push    rdi
0x18000b042  sub     rsp, 20h
0x18000b046  mov     rdi, rdx
0x18000b049  mov     qword ptr [rdx], 0
0x18000b050  lea     rdx, [rsp+28h+arg_8]
0x18000b055  mov     [rsp+28h+arg_8], 0
0x18000b05e  call    cs:__imp_RoActivateInstance
0x18000b065  nop     dword ptr [rax+rax+00h]
0x18000b06a  mov     ebx, eax
0x18000b06c  test    eax, eax
0x18000b06e  js      short loc_18000B0BF
0x18000b070  mov     r8d, 10h; Size
0x18000b076  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000b07d  lea     rcx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e; Buf1
0x18000b084  call    memcmp_0
0x18000b089  mov     rcx, [rsp+28h+arg_8]
0x18000b08e  test    eax, eax
0x18000b090  jnz     short loc_18000B097
0x18000b092  mov     [rdi], rcx
0x18000b095  jmp     short loc_18000B0BF
0x18000b097  mov     rax, [rcx]
0x18000b09a  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000b0a1  mov     r8, rdi
0x18000b0a4  mov     rax, [rax]
0x18000b0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ac  mov     rcx, [rsp+28h+arg_8]
0x18000b0b1  mov     ebx, eax
0x18000b0b3  mov     rax, [rcx]
0x18000b0b6  mov     rax, [rax+10h]
0x18000b0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bf  mov     eax, ebx
0x18000b0c1  mov     rbx, [rsp+28h+arg_0]
0x18000b0c6  add     rsp, 20h
0x18000b0ca  pop     rdi
0x18000b0cb  retn
```
