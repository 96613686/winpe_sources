# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001cdd0`
- end: `0x18001ce31`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextCompositionInfoUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001cdd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cdf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cdf2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_757c2094_9eb8_465a_8f3f_c5f2c541ca98;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001cdd0  mov     [rsp+arg_0], rbx
0x18001cdd5  push    rdi
0x18001cdd6  sub     rsp, 20h
0x18001cdda  mov     qword ptr [r8], 0
0x18001cde1  mov     ecx, 20h ; ' '; cb
0x18001cde6  mov     dword ptr [rdx], 0
0x18001cdec  mov     rbx, r8
0x18001cdef  mov     rdi, rdx
0x18001cdf2  call    cs:__imp_CoTaskMemAlloc
0x18001cdf8  test    rax, rax
0x18001cdfb  jnz     short loc_18001CE04
0x18001cdfd  mov     eax, 8007000Eh
0x18001ce02  jmp     short loc_18001CE26
0x18001ce04  movups  xmm0, xmmword ptr cs:_GUID_757c2094_9eb8_465a_8f3f_c5f2c541ca98.Data1
0x18001ce0b  movdqu  xmmword ptr [rax], xmm0
0x18001ce0f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001ce16  movdqu  xmmword ptr [rax+10h], xmm1
0x18001ce1b  mov     dword ptr [rdi], 2
0x18001ce21  mov     [rbx], rax
0x18001ce24  xor     eax, eax
0x18001ce26  mov     rbx, [rsp+28h+arg_0]
0x18001ce2b  add     rsp, 20h
0x18001ce2f  pop     rdi
0x18001ce30  retn
```
