# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IDownloadManager,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800181a0`
- end: `0x1800181ff`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDownloadManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017714`
- `0x1800181a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IDownloadManager,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IDownloadManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800181a0  mov     [rsp+arg_0], rbx
0x1800181a5  push    rdi
0x1800181a6  sub     rsp, 20h
0x1800181aa  mov     qword ptr [r8], 0
0x1800181b1  mov     ecx, 20h ; ' '; cb
0x1800181b6  mov     dword ptr [rdx], 0
0x1800181bc  mov     rbx, r8
0x1800181bf  mov     rdi, rdx
0x1800181c2  call    cs:__imp_CoTaskMemAlloc
0x1800181c8  mov     r8, rax
0x1800181cb  test    rax, rax
0x1800181ce  jnz     short loc_1800181D7
0x1800181d0  mov     eax, 8007000Eh
0x1800181d5  jmp     short loc_1800181F4
0x1800181d7  lea     rdx, [rsp+28h+arg_8]
0x1800181dc  mov     [rsp+28h+arg_8], 0
0x1800181e4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIDownloadManager@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IDownloadManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800181e9  mov     dword ptr [rdi], 2
0x1800181ef  xor     eax, eax
0x1800181f1  mov     [rbx], r8
0x1800181f4  mov     rbx, [rsp+28h+arg_0]
0x1800181f9  add     rsp, 20h
0x1800181fd  pop     rdi
0x1800181fe  retn
```
