# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<IInspectable *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015b70`
- end: `0x180015bd1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAUIInspectable@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015b70`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015b92`
- `ole32!CoTaskMemAlloc` at `0x180015b92`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<IInspectable *>,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_44a94f2d_04f8_5091_b336_be7892dd10be;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180015b70  mov     [rsp+arg_0], rbx
0x180015b75  push    rdi
0x180015b76  sub     rsp, 20h
0x180015b7a  mov     qword ptr [r8], 0
0x180015b81  mov     ecx, 20h ; ' '; cb
0x180015b86  mov     dword ptr [rdx], 0
0x180015b8c  mov     rbx, r8
0x180015b8f  mov     rdi, rdx
0x180015b92  call    cs:__imp_CoTaskMemAlloc
0x180015b98  test    rax, rax
0x180015b9b  jnz     short loc_180015BA4
0x180015b9d  mov     eax, 8007000Eh
0x180015ba2  jmp     short loc_180015BC6
0x180015ba4  movups  xmm0, xmmword ptr cs:_GUID_44a94f2d_04f8_5091_b336_be7892dd10be.Data1
0x180015bab  movdqu  xmmword ptr [rax], xmm0
0x180015baf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015bb6  movdqu  xmmword ptr [rax+10h], xmm1
0x180015bbb  mov     dword ptr [rdi], 2
0x180015bc1  mov     [rbx], rax
0x180015bc4  xor     eax, eax
0x180015bc6  mov     rbx, [rsp+28h+arg_0]
0x180015bcb  add     rsp, 20h
0x180015bcf  pop     rdi
0x180015bd0  retn
```
