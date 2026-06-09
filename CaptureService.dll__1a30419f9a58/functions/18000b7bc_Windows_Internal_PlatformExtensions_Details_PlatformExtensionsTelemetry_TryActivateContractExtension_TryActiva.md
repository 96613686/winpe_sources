# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::TryActivateContractExtension(wistd::integral_constant<char,0>,HSTRING__ * &,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,_GUID const &)

- ea: `0x18000b7bc`
- end: `0x18000b88e`
- name: `??$?0AEAPEAUHSTRING__@@AEAUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@AEBU_GUID@@@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@AEAA@U?$integral_constant@D$0A@@wistd@@AEAPEAUHSTRING__@@AEAUWindowId@WindowManagement@ApplicationModel@45@AEBU_GUID@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015d0c`

## callees

- `0x180003bc8`
- `0x180014dd4`

## string_xrefs

- `0x18000b7e3`: `TryActivateContractExtension`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::TryActivateContractExtension(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  __int64 v8; // rbx
  _QWORD *v9; // rcx

  v8 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = "TryActivateContractExtension";
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  v9 = (_QWORD *)(a1 + 88);
  v9[19] = 0;
  v9[20] = 0;
  memset_0(v9, 0, 0x98u);
  *(_DWORD *)(v8 + 248) = 1;
  *(_QWORD *)(v8 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v8;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = a1 + 48;
  *(_BYTE *)(a1 + 328) = 0;
  *(_QWORD *)a1 = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    a1,
    *a3,
    *a4,
    a5);
  return a1;
}

```

## disassembly

```asm
0x18000b7bc  push    rbx
0x18000b7be  push    rbp
0x18000b7bf  push    rsi
0x18000b7c0  push    rdi
0x18000b7c1  push    r14
0x18000b7c3  sub     rsp, 20h
0x18000b7c7  mov     rdi, r9
0x18000b7ca  mov     rsi, r8
0x18000b7cd  mov     r14, rcx
0x18000b7d0  lea     rbx, [rcx+8]
0x18000b7d4  xor     ebp, ebp
0x18000b7d6  mov     [rbx], ebp
0x18000b7d8  mov     [rbx+4], bpl
0x18000b7dc  mov     [rbx+40h], bpl
0x18000b7e0  mov     [rbx+28h], ebp
0x18000b7e3  lea     rax, aTryactivatecon; "TryActivateContractExtension"
0x18000b7ea  mov     [rbx+30h], rax
0x18000b7ee  mov     [rbx+38h], rbp
0x18000b7f2  mov     [rbx+48h], ebp
0x18000b7f5  lea     rcx, [rbx+50h]; void *
0x18000b7f9  mov     [rcx+98h], rbp
0x18000b800  mov     [rcx+0A0h], rbp
0x18000b807  xor     edx, edx; Val
0x18000b809  mov     r8d, 98h; Size
0x18000b80f  call    memset_0
0x18000b814  mov     dword ptr [rbx+0F8h], 1
0x18000b81e  xor     eax, eax
0x18000b820  mov     [rbx+100h], rax
0x18000b827  mov     [r14+110h], rbx
0x18000b82e  mov     [r14+118h], rbp
0x18000b835  mov     [r14+120h], rbp
0x18000b83c  mov     [r14+128h], r14
0x18000b843  mov     [r14+130h], rbp
0x18000b84a  mov     [r14+138h], ebp
0x18000b851  lea     rax, [r14+30h]
0x18000b855  mov     [r14+140h], rax
0x18000b85c  mov     [r14+148h], bpl
0x18000b863  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x18000b86a  mov     [r14], rax
0x18000b86d  mov     r9, [rsp+48h+arg_20]
0x18000b872  mov     r8d, [rdi]
0x18000b875  mov     rdx, [rsi]
0x18000b878  mov     rcx, r14
0x18000b87b  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x18000b880  mov     rax, r14
0x18000b883  add     rsp, 20h
0x18000b887  pop     r14
0x18000b889  pop     rdi
0x18000b88a  pop     rsi
0x18000b88b  pop     rbp
0x18000b88c  pop     rbx
0x18000b88d  retn
```
