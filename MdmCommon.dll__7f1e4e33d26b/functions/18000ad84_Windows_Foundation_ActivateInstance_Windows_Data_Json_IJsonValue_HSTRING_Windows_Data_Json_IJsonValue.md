# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000ad84`
- end: `0x18000ae0e`
- name: `??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ba7c`
- `0x18000ef34`

## callees

- `0x18000ad84`
- `0x18001d504`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000ada6`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000ada6`

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
0x18000ad84  mov     [rsp+arg_0], rbx
0x18000ad89  push    rdi
0x18000ad8a  sub     rsp, 20h
0x18000ad8e  mov     rdi, rdx
0x18000ad91  mov     qword ptr [rdx], 0
0x18000ad98  lea     rdx, [rsp+28h+arg_8]
0x18000ad9d  mov     [rsp+28h+arg_8], 0
0x18000ada6  call    cs:__imp_RoActivateInstance
0x18000adac  mov     ebx, eax
0x18000adae  test    eax, eax
0x18000adb0  js      short loc_18000AE01
0x18000adb2  mov     r8d, 10h; Size
0x18000adb8  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000adbf  lea     rcx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e; Buf1
0x18000adc6  call    memcmp_0
0x18000adcb  mov     rcx, [rsp+28h+arg_8]
0x18000add0  test    eax, eax
0x18000add2  jnz     short loc_18000ADD9
0x18000add4  mov     [rdi], rcx
0x18000add7  jmp     short loc_18000AE01
0x18000add9  mov     rax, [rcx]
0x18000addc  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000ade3  mov     r8, rdi
0x18000ade6  mov     rax, [rax]
0x18000ade9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adee  mov     rcx, [rsp+28h+arg_8]
0x18000adf3  mov     ebx, eax
0x18000adf5  mov     rax, [rcx]
0x18000adf8  mov     rax, [rax+10h]
0x18000adfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae01  mov     eax, ebx
0x18000ae03  mov     rbx, [rsp+28h+arg_0]
0x18000ae08  add     rsp, 20h
0x18000ae0c  pop     rdi
0x18000ae0d  retn
```
