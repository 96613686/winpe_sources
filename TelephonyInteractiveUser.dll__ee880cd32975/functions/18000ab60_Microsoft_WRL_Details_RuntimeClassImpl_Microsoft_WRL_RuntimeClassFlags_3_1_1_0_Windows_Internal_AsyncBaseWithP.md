# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(ulong *,_GUID * *)

- ea: `0x18000ab60`
- end: `0x18000abd9`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@_N@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000abe0`

## callees

- `0x18000ab60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ab82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ab82`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(
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
  *v5 = GUID_00000036_0000_0000_c000_000000000046;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a;
  v5[3] = GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000ab60  mov     [rsp+arg_0], rbx
0x18000ab65  push    rdi
0x18000ab66  sub     rsp, 20h
0x18000ab6a  mov     qword ptr [r8], 0
0x18000ab71  mov     ecx, 40h ; '@'; cb
0x18000ab76  mov     dword ptr [rdx], 0
0x18000ab7c  mov     rbx, r8
0x18000ab7f  mov     rdi, rdx
0x18000ab82  call    cs:__imp_CoTaskMemAlloc
0x18000ab88  test    rax, rax
0x18000ab8b  jnz     short loc_18000AB94
0x18000ab8d  mov     eax, 8007000Eh
0x18000ab92  jmp     short loc_18000ABCE
0x18000ab94  movups  xmm0, xmmword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data1
0x18000ab9b  movdqu  xmmword ptr [rax], xmm0
0x18000ab9f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000aba6  movdqu  xmmword ptr [rax+10h], xmm1
0x18000abab  movups  xmm0, xmmword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data1
0x18000abb2  movdqu  xmmword ptr [rax+20h], xmm0
0x18000abb7  movups  xmm1, xmmword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data1
0x18000abbe  movdqu  xmmword ptr [rax+30h], xmm1
0x18000abc3  mov     dword ptr [rdi], 4
0x18000abc9  mov     [rbx], rax
0x18000abcc  xor     eax, eax
0x18000abce  mov     rbx, [rsp+28h+arg_0]
0x18000abd3  add     rsp, 20h
0x18000abd7  pop     rdi
0x18000abd8  retn
```
