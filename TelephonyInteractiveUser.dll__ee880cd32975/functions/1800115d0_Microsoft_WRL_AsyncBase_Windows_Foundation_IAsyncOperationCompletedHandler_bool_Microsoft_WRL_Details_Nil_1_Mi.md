# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(uint)

- ea: `0x1800115d0`
- end: `0x180011660`
- name: `?put_Id@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJI@Z`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800115d0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001163f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001163f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001160c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001160c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(
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
      RoOriginateError(2147483662LL);
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
0x1800115d0  sub     rsp, 48h
0x1800115d4  mov     rax, cs:__security_cookie
0x1800115db  xor     rax, rsp
0x1800115de  mov     [rsp+48h+var_18], rax
0x1800115e3  test    edx, edx
0x1800115e5  jnz     short loc_180011619
0x1800115e7  mov     eax, dword ptr cs:aId; "id"
0x1800115ed  lea     r8, [rsp+48h+var_24]
0x1800115f2  mov     [rsp+48h+var_24], eax
0x1800115f6  mov     edx, 2
0x1800115fb  movzx   eax, word ptr cs:aId+4; ""
0x180011602  mov     ecx, 80070057h
0x180011607  mov     [rsp+48h+var_20], ax
0x18001160c  call    cs:__imp_RoOriginateErrorW
0x180011612  mov     eax, 80070057h
0x180011617  jmp     short loc_18001164E
0x180011619  mov     [rcx+40h], edx
0x18001161c  mov     ecx, [rcx+38h]
0x18001161f  mov     [rsp+48h+var_28], 0FFFFFFFEh
0x180011627  mov     eax, [rsp+48h+var_28]
0x18001162b  lock cmpxchg [rsp+48h+var_28], ecx
0x180011631  cmp     [rsp+48h+var_28], 0FFFFFFFFh
0x180011636  jz      short loc_18001164C
0x180011638  xor     edx, edx
0x18001163a  mov     ecx, 8000000Eh
0x18001163f  call    cs:__imp_RoOriginateError
0x180011645  mov     eax, 8000000Eh
0x18001164a  jmp     short loc_18001164E
0x18001164c  xor     eax, eax
0x18001164e  mov     rcx, [rsp+48h+var_18]
0x180011653  xor     rcx, rsp; StackCookie
0x180011656  call    __security_check_cookie
0x18001165b  add     rsp, 48h
0x18001165f  retn
```
