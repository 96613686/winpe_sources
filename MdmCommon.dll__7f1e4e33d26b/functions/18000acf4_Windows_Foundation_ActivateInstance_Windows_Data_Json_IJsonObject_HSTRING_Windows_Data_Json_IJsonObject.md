# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)

- ea: `0x18000acf4`
- end: `0x18000ad7e`
- name: `??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ae24`
- `0x18000b350`
- `0x18000ba7c`
- `0x18000c38c`
- `0x18000e97c`
- `0x18000ef34`

## callees

- `0x18000acf4`
- `0x18001d504`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000ad16`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000ad16`

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
0x18000acf4  mov     [rsp+arg_0], rbx
0x18000acf9  push    rdi
0x18000acfa  sub     rsp, 20h
0x18000acfe  mov     rdi, rdx
0x18000ad01  mov     qword ptr [rdx], 0
0x18000ad08  lea     rdx, [rsp+28h+arg_8]
0x18000ad0d  mov     [rsp+28h+arg_8], 0
0x18000ad16  call    cs:__imp_RoActivateInstance
0x18000ad1c  mov     ebx, eax
0x18000ad1e  test    eax, eax
0x18000ad20  js      short loc_18000AD71
0x18000ad22  mov     r8d, 10h; Size
0x18000ad28  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000ad2f  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x18000ad36  call    memcmp_0
0x18000ad3b  mov     rcx, [rsp+28h+arg_8]
0x18000ad40  test    eax, eax
0x18000ad42  jnz     short loc_18000AD49
0x18000ad44  mov     [rdi], rcx
0x18000ad47  jmp     short loc_18000AD71
0x18000ad49  mov     rax, [rcx]
0x18000ad4c  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18000ad53  mov     r8, rdi
0x18000ad56  mov     rax, [rax]
0x18000ad59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad5e  mov     rcx, [rsp+28h+arg_8]
0x18000ad63  mov     ebx, eax
0x18000ad65  mov     rax, [rcx]
0x18000ad68  mov     rax, [rax+10h]
0x18000ad6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad71  mov     eax, ebx
0x18000ad73  mov     rbx, [rsp+28h+arg_0]
0x18000ad78  add     rsp, 20h
0x18000ad7c  pop     rdi
0x18000ad7d  retn
```
