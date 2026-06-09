# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,uchar> *>>::GetIids(ulong *,_GUID * *)

- ea: `0x180014fe0`
- end: `0x180015041`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAU?$IKeyValuePair@PEAUHSTRING__@@E@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015002`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,unsigned char> *>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_bdea44aa_b64a_56b5_8636_9ae88b242de1;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180014fe0  mov     [rsp+arg_0], rbx
0x180014fe5  push    rdi
0x180014fe6  sub     rsp, 20h
0x180014fea  mov     qword ptr [r8], 0
0x180014ff1  mov     ecx, 20h ; ' '; cb
0x180014ff6  mov     dword ptr [rdx], 0
0x180014ffc  mov     rbx, r8
0x180014fff  mov     rdi, rdx
0x180015002  call    cs:__imp_CoTaskMemAlloc
0x180015008  test    rax, rax
0x18001500b  jnz     short loc_180015014
0x18001500d  mov     eax, 8007000Eh
0x180015012  jmp     short loc_180015036
0x180015014  movups  xmm0, xmmword ptr cs:_GUID_bdea44aa_b64a_56b5_8636_9ae88b242de1.Data1
0x18001501b  movdqu  xmmword ptr [rax], xmm0
0x18001501f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015026  movdqu  xmmword ptr [rax+10h], xmm1
0x18001502b  mov     dword ptr [rdi], 2
0x180015031  mov     [rbx], rax
0x180015034  xor     eax, eax
0x180015036  mov     rbx, [rsp+28h+arg_0]
0x18001503b  add     rsp, 20h
0x18001503f  pop     rdi
0x180015040  retn
```
