# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)

- ea: `0x1800139c8`
- end: `0x180013a52`
- name: `??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015504`
- `0x180015fbc`
- `0x18001691c`
- `0x18001e164`
- `0x180020068`
- `0x180020d2c`
- `0x18002166c`
- `0x180022240`
- `0x180027dc8`

## callees

- `0x180002f9c`
- `0x1800139c8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800139ea`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800139ea`

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
0x1800139c8  mov     [rsp+arg_0], rbx
0x1800139cd  push    rdi
0x1800139ce  sub     rsp, 20h
0x1800139d2  mov     rdi, rdx
0x1800139d5  mov     qword ptr [rdx], 0
0x1800139dc  lea     rdx, [rsp+28h+arg_8]
0x1800139e1  mov     [rsp+28h+arg_8], 0
0x1800139ea  call    cs:__imp_RoActivateInstance
0x1800139f0  mov     ebx, eax
0x1800139f2  test    eax, eax
0x1800139f4  js      short loc_180013A45
0x1800139f6  mov     r8d, 10h; Size
0x1800139fc  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180013a03  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x180013a0a  call    memcmp_0
0x180013a0f  mov     rcx, [rsp+28h+arg_8]
0x180013a14  test    eax, eax
0x180013a16  jnz     short loc_180013A1D
0x180013a18  mov     [rdi], rcx
0x180013a1b  jmp     short loc_180013A45
0x180013a1d  mov     rax, [rcx]
0x180013a20  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x180013a27  mov     r8, rdi
0x180013a2a  mov     rax, [rax]
0x180013a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a32  mov     rcx, [rsp+28h+arg_8]
0x180013a37  mov     ebx, eax
0x180013a39  mov     rax, [rcx]
0x180013a3c  mov     rax, [rax+10h]
0x180013a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a45  mov     eax, ebx
0x180013a47  mov     rbx, [rsp+28h+arg_0]
0x180013a4c  add     rsp, 20h
0x180013a50  pop     rdi
0x180013a51  retn
```
