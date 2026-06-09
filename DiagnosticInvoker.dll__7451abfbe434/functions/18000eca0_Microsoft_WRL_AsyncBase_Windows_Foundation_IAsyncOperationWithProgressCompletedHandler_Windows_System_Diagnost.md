# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(uint)

- ea: `0x18000eca0`
- end: `0x18000ed30`
- name: `?put_Id@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJI@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e20`
- `0x18000eca0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000ecdc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000ecdc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ed0f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ed0f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(
        __int64 a1,
        int a2)
{
  signed __int32 v3; // ecx
  signed __int32 v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+24h] [rbp-24h] BYREF
  wchar_t v6; // [rsp+28h] [rbp-20h]

  if ( a2 )
  {
    *(_DWORD *)(a1 + 64) = a2;
    v3 = *(_DWORD *)(a1 + 56);
    v4 = -2;
    _InterlockedCompareExchange(&v4, v3, -2);
    if ( v4 == -1 )
    {
      return 0;
    }
    else
    {
      RoOriginateError(2147483662LL, 0);
      return 2147483662LL;
    }
  }
  else
  {
    v5 = *(_DWORD *)L"id";
    v6 = aId[2];
    RoOriginateErrorW(2147942487LL, 2, &v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000eca0  sub     rsp, 48h
0x18000eca4  mov     rax, cs:__security_cookie
0x18000ecab  xor     rax, rsp
0x18000ecae  mov     [rsp+48h+var_18], rax
0x18000ecb3  test    edx, edx
0x18000ecb5  jnz     short loc_18000ECE9
0x18000ecb7  mov     eax, dword ptr cs:aId; "id"
0x18000ecbd  lea     r8, [rsp+48h+var_24]
0x18000ecc2  mov     [rsp+48h+var_24], eax
0x18000ecc6  mov     edx, 2
0x18000eccb  movzx   eax, word ptr cs:aId+4; ""
0x18000ecd2  mov     ecx, 80070057h
0x18000ecd7  mov     [rsp+48h+var_20], ax
0x18000ecdc  call    cs:__imp_RoOriginateErrorW
0x18000ece2  mov     eax, 80070057h
0x18000ece7  jmp     short loc_18000ED1E
0x18000ece9  mov     [rcx+40h], edx
0x18000ecec  mov     ecx, [rcx+38h]
0x18000ecef  mov     [rsp+48h+var_28], 0FFFFFFFEh
0x18000ecf7  mov     eax, [rsp+48h+var_28]
0x18000ecfb  lock cmpxchg [rsp+48h+var_28], ecx
0x18000ed01  cmp     [rsp+48h+var_28], 0FFFFFFFFh
0x18000ed06  jz      short loc_18000ED1C
0x18000ed08  xor     edx, edx
0x18000ed0a  mov     ecx, 8000000Eh
0x18000ed0f  call    cs:__imp_RoOriginateError
0x18000ed15  mov     eax, 8000000Eh
0x18000ed1a  jmp     short loc_18000ED1E
0x18000ed1c  xor     eax, eax
0x18000ed1e  mov     rcx, [rsp+48h+var_18]
0x18000ed23  xor     rcx, rsp; StackCookie
0x18000ed26  call    __security_check_cookie
0x18000ed2b  add     rsp, 48h
0x18000ed2f  retn
```
