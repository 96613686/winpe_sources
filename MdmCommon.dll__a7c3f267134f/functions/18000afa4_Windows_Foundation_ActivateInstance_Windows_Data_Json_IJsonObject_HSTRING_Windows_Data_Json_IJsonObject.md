# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)

- ea: `0x18000afa4`
- end: `0x18000b035`
- name: `??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b0e4`
- `0x18000b634`
- `0x18000bd94`
- `0x18000c6e8`
- `0x18000edc0`
- `0x18000f3b8`

## callees

- `0x18000afa4`
- `0x18001dbe4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000afc6`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000afc6`

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
0x18000afa4  mov     [rsp+arg_0], rbx
0x18000afa9  push    rdi
0x18000afaa  sub     rsp, 20h
0x18000afae  mov     rdi, rdx
0x18000afb1  mov     qword ptr [rdx], 0
0x18000afb8  lea     rdx, [rsp+28h+arg_8]
0x18000afbd  mov     [rsp+28h+arg_8], 0
0x18000afc6  call    cs:__imp_RoActivateInstance
0x18000afcd  nop     dword ptr [rax+rax+00h]
0x18000afd2  mov     ebx, eax
0x18000afd4  test    eax, eax
0x18000afd6  js      short loc_18000B027
0x18000afd8  mov     r8d, 10h; Size
0x18000afde  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000afe5  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x18000afec  call    memcmp_0
0x18000aff1  mov     rcx, [rsp+28h+arg_8]
0x18000aff6  test    eax, eax
0x18000aff8  jnz     short loc_18000AFFF
0x18000affa  mov     [rdi], rcx
0x18000affd  jmp     short loc_18000B027
0x18000afff  mov     rax, [rcx]
0x18000b002  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18000b009  mov     r8, rdi
0x18000b00c  mov     rax, [rax]
0x18000b00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b014  mov     rcx, [rsp+28h+arg_8]
0x18000b019  mov     ebx, eax
0x18000b01b  mov     rax, [rcx]
0x18000b01e  mov     rax, [rax+10h]
0x18000b022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b027  mov     eax, ebx
0x18000b029  mov     rbx, [rsp+28h+arg_0]
0x18000b02e  add     rsp, 20h
0x18000b032  pop     rdi
0x18000b033  retn
```
