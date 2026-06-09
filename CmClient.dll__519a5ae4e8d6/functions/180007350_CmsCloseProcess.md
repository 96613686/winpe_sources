# CmsCloseProcess

- ea: `0x180007350`
- end: `0x1800073f4`
- name: `CmsCloseProcess`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a430`
- `0x18000a990`

## callees

- `0x180001944`
- `0x1800021dc`
- `0x180003c74`
- `0x1800066e4`
- `0x180007350`

## string_xrefs

- `0x180007390`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCloseProcess(__int64 **a1)
{
  __int64 *v1; // rbx
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  void *v6; // rdi
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = *a1;
  v9 = **a1;
  v10 = &v9;
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_CloseProcess,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v6 = (void *)v1[4];
    v1[4] = 0;
    if ( v6 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v6);
      operator delete(v6, (const struct std::nothrow_t *)0x18);
    }
    operator delete(v1, (const struct std::nothrow_t *)0x28);
    result = 0;
    *a1 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v3,
      v7);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180007350  mov     r11, rsp
0x180007353  mov     [r11+18h], rbx
0x180007357  mov     [r11+20h], rsi
0x18000735b  push    rdi; int
0x18000735c  sub     rsp, 20h
0x180007360  mov     rbx, [rcx]
0x180007363  lea     rdx, [r11+10h]
0x180007367  mov     rsi, rcx
0x18000736a  lea     rcx, CmsRpcClt_CloseProcess
0x180007371  mov     rax, [rbx]
0x180007374  mov     [r11+8], rax
0x180007378  lea     rax, [r11+8]
0x18000737c  mov     [r11+10h], rax
0x180007380  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180007385  mov     edi, eax
0x180007387  test    eax, eax
0x180007389  jns     short loc_1800073A8
0x18000738b  mov     rcx, [rsp+28h]; this
0x180007390  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007397  mov     r9d, eax; char *
0x18000739a  mov     edx, 386h; void *
0x18000739f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073a4  mov     eax, edi
0x1800073a6  jmp     short loc_1800073E4
0x1800073a8  mov     rdi, [rbx+20h]
0x1800073ac  mov     qword ptr [rbx+20h], 0
0x1800073b4  test    rdi, rdi
0x1800073b7  jz      short loc_1800073CE
0x1800073b9  mov     rcx, rdi
0x1800073bc  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x1800073c1  mov     edx, 18h; struct std::nothrow_t *
0x1800073c6  mov     rcx, rdi; void *
0x1800073c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800073ce  mov     edx, 28h ; '('; struct std::nothrow_t *
0x1800073d3  mov     rcx, rbx; void *
0x1800073d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800073db  xor     eax, eax
0x1800073dd  mov     qword ptr [rsi], 0
0x1800073e4  mov     rbx, [rsp+28h+arg_10]
0x1800073e9  mov     rsi, [rsp+28h+arg_18]
0x1800073ee  add     rsp, 20h
0x1800073f2  pop     rdi
0x1800073f3  retn
```
