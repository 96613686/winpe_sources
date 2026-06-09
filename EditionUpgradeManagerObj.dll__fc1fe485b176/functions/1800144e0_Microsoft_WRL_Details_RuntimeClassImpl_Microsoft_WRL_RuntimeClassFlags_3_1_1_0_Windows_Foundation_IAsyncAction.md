# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800144e0`
- end: `0x180014559`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014560`

## callees

- `0x1800144e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014502`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_44825c7c_0da9_5691_b2b4_914f231eeced;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  v5[3] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800144e0  mov     [rsp+arg_0], rbx
0x1800144e5  push    rdi
0x1800144e6  sub     rsp, 20h
0x1800144ea  mov     qword ptr [r8], 0
0x1800144f1  mov     ecx, 40h ; '@'; cb
0x1800144f6  mov     dword ptr [rdx], 0
0x1800144fc  mov     rbx, r8
0x1800144ff  mov     rdi, rdx
0x180014502  call    cs:__imp_CoTaskMemAlloc
0x180014508  test    rax, rax
0x18001450b  jnz     short loc_180014514
0x18001450d  mov     eax, 8007000Eh
0x180014512  jmp     short loc_18001454E
0x180014514  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001451b  movdqu  xmmword ptr [rax], xmm0
0x18001451f  movups  xmm1, xmmword ptr cs:_GUID_44825c7c_0da9_5691_b2b4_914f231eeced.Data1
0x180014526  movdqu  xmmword ptr [rax+10h], xmm1
0x18001452b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180014532  movdqu  xmmword ptr [rax+20h], xmm0
0x180014537  movups  xmm1, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001453e  movdqu  xmmword ptr [rax+30h], xmm1
0x180014543  mov     dword ptr [rdi], 4
0x180014549  mov     [rbx], rax
0x18001454c  xor     eax, eax
0x18001454e  mov     rbx, [rsp+28h+arg_0]
0x180014553  add     rsp, 20h
0x180014557  pop     rdi
0x180014558  retn
```
