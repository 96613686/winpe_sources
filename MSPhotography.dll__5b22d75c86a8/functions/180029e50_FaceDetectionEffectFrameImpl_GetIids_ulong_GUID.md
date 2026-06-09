# FaceDetectionEffectFrameImpl::GetIids(ulong *,_GUID * *)

- ea: `0x180029e50`
- end: `0x180029ed8`
- name: `?GetIids@FaceDetectionEffectFrameImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(FaceDetectionEffectFrameImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029ee0`
- `0x180029ef0`

## callees

- `0x180029d40`
- `0x180029e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e72`

## pseudocode

```c
__int64 __fastcall FaceDetectionEffectFrameImpl::GetIids(
        FaceDetectionEffectFrameImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // rcx
  struct _GUID *v9; // r8
  int v10; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  v10 = 0;
  Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v10,
    v6);
  v8 = (unsigned int)(v10 + 1);
  v9[v10] = GUID_00000038_0000_0000_c000_000000000046;
  result = 0;
  v9[v8] = GUID_8ab08993_5dc8_447b_a247_5270bd802ece;
  *a2 = 4;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x180029e50  mov     [rsp+arg_0], rbx
0x180029e55  push    rdi
0x180029e56  sub     rsp, 20h
0x180029e5a  mov     qword ptr [r8], 0
0x180029e61  mov     ecx, 40h ; '@'; cb
0x180029e66  mov     dword ptr [rdx], 0
0x180029e6c  mov     rbx, r8
0x180029e6f  mov     rdi, rdx
0x180029e72  call    cs:__imp_CoTaskMemAlloc
0x180029e78  mov     r8, rax
0x180029e7b  test    rax, rax
0x180029e7e  jnz     short loc_180029E87
0x180029e80  mov     eax, 8007000Eh
0x180029e85  jmp     short loc_180029ECD
0x180029e87  lea     rdx, [rsp+28h+arg_8]
0x180029e8c  mov     [rsp+28h+arg_8], 0
0x180029e94  call    ?FillArrayWithIid@?$Implements@UIMediaFrame@Media@Windows@@UIClosable@Foundation@3@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180029e99  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180029ea0  mov     edx, [rsp+28h+arg_8]
0x180029ea4  mov     eax, edx
0x180029ea6  add     rax, rax
0x180029ea9  lea     ecx, [rdx+1]
0x180029eac  add     rcx, rcx
0x180029eaf  movdqu  xmmword ptr [r8+rax*8], xmm0
0x180029eb5  xor     eax, eax
0x180029eb7  movups  xmm0, xmmword ptr cs:_GUID_8ab08993_5dc8_447b_a247_5270bd802ece.Data1
0x180029ebe  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x180029ec4  mov     dword ptr [rdi], 4
0x180029eca  mov     [rbx], r8
0x180029ecd  mov     rbx, [rsp+28h+arg_0]
0x180029ed2  add     rsp, 20h
0x180029ed6  pop     rdi
0x180029ed7  retn
```
