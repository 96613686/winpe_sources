# FuseOperation::GetIids(ulong *,_GUID * *)

- ea: `0x18002dbe0`
- end: `0x18002dc4a`
- name: `?GetIids@FuseOperation@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(FuseOperation *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002dc50`

## callees

- `0x18002d81c`
- `0x18002dbe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dc02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dc02`

## pseudocode

```c
__int64 __fastcall FuseOperation::GetIids(FuseOperation *this, unsigned int *a2, struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_7cf3d802_9d4a_5f56_b6b0_9569b5494507;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::System::Threading::IWorkItemHandler>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18002dbe0  mov     [rsp+arg_0], rbx
0x18002dbe5  push    rdi
0x18002dbe6  sub     rsp, 20h
0x18002dbea  mov     qword ptr [r8], 0
0x18002dbf1  mov     ecx, 30h ; '0'; cb
0x18002dbf6  mov     dword ptr [rdx], 0
0x18002dbfc  mov     rbx, r8
0x18002dbff  mov     rdi, rdx
0x18002dc02  call    cs:__imp_CoTaskMemAlloc
0x18002dc08  mov     r8, rax
0x18002dc0b  test    rax, rax
0x18002dc0e  jnz     short loc_18002DC17
0x18002dc10  mov     eax, 8007000Eh
0x18002dc15  jmp     short loc_18002DC3F
0x18002dc17  movups  xmm0, xmmword ptr cs:_GUID_7cf3d802_9d4a_5f56_b6b0_9569b5494507.Data1
0x18002dc1e  lea     rdx, [rsp+28h+arg_8]
0x18002dc23  mov     [rsp+28h+arg_8], 1
0x18002dc2b  movdqu  xmmword ptr [rax], xmm0
0x18002dc2f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIWorkItemHandler@Threading@System@Windows@@@23@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::System::Threading::IWorkItemHandler>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x18002dc34  mov     dword ptr [rdi], 3
0x18002dc3a  xor     eax, eax
0x18002dc3c  mov     [rbx], r8
0x18002dc3f  mov     rbx, [rsp+28h+arg_0]
0x18002dc44  add     rsp, 20h
0x18002dc48  pop     rdi
0x18002dc49  retn
```
