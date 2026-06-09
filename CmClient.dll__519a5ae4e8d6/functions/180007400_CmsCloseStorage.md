# CmsCloseStorage

- ea: `0x180007400`
- end: `0x18000747e`
- name: `CmsCloseStorage`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180001944`
- `0x1800021dc`
- `0x1800066e4`
- `0x180007400`

## string_xrefs

- `0x180007440`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCloseStorage(__int64 **a1)
{
  __int64 *v1; // rsi
  int v3; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v9; // [rsp+38h] [rbp+10h] BYREF

  v1 = *a1;
  v8 = **a1;
  v9 = &v8;
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_CloseStorage,
         &v9);
  v4 = v3;
  if ( v3 >= 0 )
  {
    operator delete(v1, (const struct std::nothrow_t *)0x18);
    result = 0;
    *a1 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v3,
      v6);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180007400  mov     r11, rsp
0x180007403  mov     [r11+18h], rbx
0x180007407  mov     [r11+20h], rsi
0x18000740b  push    rdi; int
0x18000740c  sub     rsp, 20h
0x180007410  mov     rsi, [rcx]
0x180007413  lea     rdx, [r11+10h]
0x180007417  mov     rdi, rcx
0x18000741a  lea     rcx, CmsRpcClt_CloseStorage
0x180007421  mov     rax, [rsi]
0x180007424  mov     [r11+8], rax
0x180007428  lea     rax, [r11+8]
0x18000742c  mov     [r11+10h], rax
0x180007430  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180007435  mov     ebx, eax
0x180007437  test    eax, eax
0x180007439  jns     short loc_180007458
0x18000743b  mov     rcx, [rsp+28h]; this
0x180007440  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007447  mov     r9d, eax; char *
0x18000744a  mov     edx, 57Ch; void *
0x18000744f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007454  mov     eax, ebx
0x180007456  jmp     short loc_18000746E
0x180007458  mov     edx, 18h; struct std::nothrow_t *
0x18000745d  mov     rcx, rsi; void *
0x180007460  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007465  xor     eax, eax
0x180007467  mov     qword ptr [rdi], 0
0x18000746e  mov     rbx, [rsp+28h+arg_10]
0x180007473  mov     rsi, [rsp+28h+arg_18]
0x180007478  add     rsp, 20h
0x18000747c  pop     rdi
0x18000747d  retn
```
