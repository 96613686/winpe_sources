# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)

- ea: `0x180018120`
- end: `0x1800181aa`
- name: `??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z`
- size: `138`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800185c0`
- `0x18001ada0`
- `0x180023cb0`
- `0x180024c34`
- `0x180026b60`

## callees

- `0x180009963`
- `0x180018120`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180018142`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180018142`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(__int64 a1, _QWORD *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = RoActivateInstance(a1, &v5);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v5;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v5)(
             v5,
             &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018120  mov     [rsp+arg_0], rbx
0x180018125  push    rdi
0x180018126  sub     rsp, 20h
0x18001812a  mov     rdi, rdx
0x18001812d  mov     qword ptr [rdx], 0
0x180018134  lea     rdx, [rsp+28h+arg_8]
0x180018139  mov     [rsp+28h+arg_8], 0
0x180018142  call    cs:__imp_RoActivateInstance
0x180018148  mov     ebx, eax
0x18001814a  test    eax, eax
0x18001814c  js      short loc_18001819D
0x18001814e  mov     r8d, 10h; Size
0x180018154  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001815b  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x180018162  call    memcmp_0
0x180018167  mov     rcx, [rsp+28h+arg_8]
0x18001816c  test    eax, eax
0x18001816e  jnz     short loc_180018175
0x180018170  mov     [rdi], rcx
0x180018173  jmp     short loc_18001819D
0x180018175  mov     rax, [rcx]
0x180018178  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18001817f  mov     r8, rdi
0x180018182  mov     rax, [rax]
0x180018185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001818a  mov     rcx, [rsp+28h+arg_8]
0x18001818f  mov     ebx, eax
0x180018191  mov     rax, [rcx]
0x180018194  mov     rax, [rax+10h]
0x180018198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001819d  mov     eax, ebx
0x18001819f  mov     rbx, [rsp+28h+arg_0]
0x1800181a4  add     rsp, 20h
0x1800181a8  pop     rdi
0x1800181a9  retn
```
