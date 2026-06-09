# Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)

- ea: `0x180018678`
- end: `0x180018709`
- name: `??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z`
- size: `145`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018b38`
- `0x18001b430`
- `0x180024878`
- `0x180025958`
- `0x180027b00`

## callees

- `0x1800098f3`
- `0x180018678`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001869a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001869a`

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
0x180018678  mov     [rsp+arg_0], rbx
0x18001867d  push    rdi
0x18001867e  sub     rsp, 20h
0x180018682  mov     rdi, rdx
0x180018685  mov     qword ptr [rdx], 0
0x18001868c  lea     rdx, [rsp+28h+arg_8]
0x180018691  mov     [rsp+28h+arg_8], 0
0x18001869a  call    cs:__imp_RoActivateInstance
0x1800186a1  nop     dword ptr [rax+rax+00h]
0x1800186a6  mov     ebx, eax
0x1800186a8  test    eax, eax
0x1800186aa  js      short loc_1800186FB
0x1800186ac  mov     r8d, 10h; Size
0x1800186b2  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800186b9  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x1800186c0  call    memcmp_0
0x1800186c5  mov     rcx, [rsp+28h+arg_8]
0x1800186ca  test    eax, eax
0x1800186cc  jnz     short loc_1800186D3
0x1800186ce  mov     [rdi], rcx
0x1800186d1  jmp     short loc_1800186FB
0x1800186d3  mov     rax, [rcx]
0x1800186d6  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x1800186dd  mov     r8, rdi
0x1800186e0  mov     rax, [rax]
0x1800186e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186e8  mov     rcx, [rsp+28h+arg_8]
0x1800186ed  mov     ebx, eax
0x1800186ef  mov     rax, [rcx]
0x1800186f2  mov     rax, [rax+10h]
0x1800186f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186fb  mov     eax, ebx
0x1800186fd  mov     rbx, [rsp+28h+arg_0]
0x180018702  add     rsp, 20h
0x180018706  pop     rdi
0x180018707  retn
```
