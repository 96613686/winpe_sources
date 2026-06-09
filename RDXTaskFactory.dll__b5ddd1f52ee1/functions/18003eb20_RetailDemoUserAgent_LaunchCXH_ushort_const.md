# RetailDemoUserAgent::LaunchCXH(ushort const *)

- ea: `0x18003eb20`
- end: `0x18003ebe1`
- name: `?LaunchCXH@RetailDemoUserAgent@@UEAAJPEBG@Z`
- size: `193`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aa7c`
- `0x180012b30`
- `0x180034520`
- `0x18003eb20`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003eb40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003eb40`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003eb94`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003eb94`

## string_xrefs

- `0x18003ebbd`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoUserAgent::LaunchCXH(RetailDemoUserAgent *this, const unsigned __int16 *a2)
{
  DWORD CurrentThreadId; // ebx
  __int64 *v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rcx
  int v6; // ebx
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  v8[0] = &v10;
  v8[1] = a2;
  CurrentThreadId = GetCurrentThreadId();
  v3 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7a8522e351af82ff0ec6433d09bd2ee2_____lambda_7a8522e351af82ff0ec6433d09bd2ee2___(
                    &v11,
                    v8);
  v4 = *v3;
  *v3 = 0;
  v5 = v11;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v5);
  }
  v6 = SHTaskPoolQueueTask(1, 32, CurrentThreadId);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v6 >= 0 )
    return v10;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x817,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    (const char *)(unsigned int)v6,
    v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003eb20  mov     r11, rsp
0x18003eb23  mov     [r11+8], rbx
0x18003eb27  push    rdi
0x18003eb28  sub     rsp, 40h
0x18003eb2c  mov     [rsp+48h+arg_8], 0
0x18003eb34  lea     rax, [r11+10h]
0x18003eb38  mov     [r11-18h], rax
0x18003eb3c  mov     [r11-10h], rdx
0x18003eb40  call    cs:__imp_GetCurrentThreadId
0x18003eb46  mov     ebx, eax
0x18003eb48  lea     rdx, [rsp+48h+var_18]
0x18003eb4d  lea     rcx, [rsp+48h+arg_10]
0x18003eb52  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_7a8522e351af82ff0ec6433d09bd2ee2_____lambda_7a8522e351af82ff0ec6433d09bd2ee2___
0x18003eb57  mov     rdi, [rax]
0x18003eb5a  mov     qword ptr [rax], 0
0x18003eb61  mov     rcx, [rsp+48h+arg_10]
0x18003eb66  test    rcx, rcx
0x18003eb69  jz      short loc_18003EB79
0x18003eb6b  mov     [rsp+48h+arg_10], 0
0x18003eb74  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18003eb79  mov     [rsp+48h+var_20], 0
0x18003eb82  mov     qword ptr [rsp+48h+var_28], rdi; int
0x18003eb87  xor     r9d, r9d
0x18003eb8a  mov     r8d, ebx
0x18003eb8d  lea     edx, [r9+20h]
0x18003eb91  lea     ecx, [rdx-1Fh]
0x18003eb94  call    cs:__imp_SHTaskPoolQueueTask
0x18003eb9a  mov     ebx, eax
0x18003eb9c  test    rdi, rdi
0x18003eb9f  jz      short loc_18003EBB1
0x18003eba1  mov     rdx, [rdi]
0x18003eba4  mov     rcx, rdi
0x18003eba7  mov     rax, [rdx+10h]
0x18003ebab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebb0  nop
0x18003ebb1  test    ebx, ebx
0x18003ebb3  jns     short loc_18003EBD2
0x18003ebb5  mov     rcx, [rsp+48h]; this
0x18003ebba  mov     r9d, ebx; char *
0x18003ebbd  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003ebc4  mov     edx, 817h; void *
0x18003ebc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ebce  mov     eax, ebx
0x18003ebd0  jmp     short loc_18003EBD6
0x18003ebd2  mov     eax, [rsp+48h+arg_8]
0x18003ebd6  mov     rbx, [rsp+48h+arg_0]
0x18003ebdb  add     rsp, 40h
0x18003ebdf  pop     rdi
0x18003ebe0  retn
```
