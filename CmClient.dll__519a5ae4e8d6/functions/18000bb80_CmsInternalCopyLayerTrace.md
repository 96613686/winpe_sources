# CmsInternalCopyLayerTrace

- ea: `0x18000bb80`
- end: `0x18000bc5c`
- name: `CmsInternalCopyLayerTrace`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b874`
- `0x18000bb80`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000bbe0`
- `RPCRT4!RpcBindingFree` at `0x18000bc2d`
- `RPCRT4!RpcBindingFree` at `0x18000bc44`
- `RPCRT4!RpcBindingFree` at `0x18000bbe0`
- `RPCRT4!RpcBindingFree` at `0x18000bc2d`
- `RPCRT4!RpcBindingFree` at `0x18000bc44`

## string_xrefs

- `0x18000bbbb`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000bc0c`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalCopyLayerTrace(__int64 a1, void *a2)
{
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE v11; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]

  v11 = a2;
  Binding = 0;
  v3 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v7 = Binding;
    v8 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,unsigned short const *),void *,_GUID &,unsigned short const * &>(
           v4,
           &Binding,
           a1,
           &v11);
    v9 = v8;
    if ( v8 >= 0 )
    {
      if ( v7 )
      {
        v11 = v7;
        RpcBindingFree(&v11);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x287,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
        (const char *)(unsigned int)v8,
        (int)Binding);
      if ( v7 )
      {
        v11 = v7;
        RpcBindingFree(&v11);
      }
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x281,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v3,
      (int)Binding);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v5;
  }
}

```

## disassembly

```asm
0x18000bb80  mov     [rsp-8+arg_10], rbx
0x18000bb85  mov     [rsp-8+arg_18], rdi
0x18000bb8a  push    rbp
0x18000bb8b  mov     rbp, rsp
0x18000bb8e  sub     rsp, 30h
0x18000bb92  mov     rdi, rcx
0x18000bb95  mov     [rbp+var_8], rdx
0x18000bb99  lea     rdx, [rbp+Binding]
0x18000bb9d  mov     [rbp+Binding], 0
0x18000bba5  lea     rcx, qword_180012D10; IfSpec
0x18000bbac  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000bbb1  mov     ebx, eax
0x18000bbb3  test    eax, eax
0x18000bbb5  jns     short loc_18000BBEA
0x18000bbb7  mov     rcx, [rbp+8]; this
0x18000bbbb  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bbc2  mov     r9d, eax; char *
0x18000bbc5  mov     edx, 281h; void *
0x18000bbca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bbcf  mov     rcx, [rbp+Binding]
0x18000bbd3  test    rcx, rcx
0x18000bbd6  jz      short loc_18000BBE6
0x18000bbd8  mov     [rbp+Binding], rcx
0x18000bbdc  lea     rcx, [rbp+Binding]; Binding
0x18000bbe0  call    cs:__imp_RpcBindingFree
0x18000bbe6  mov     eax, ebx
0x18000bbe8  jmp     short loc_18000BC4C
0x18000bbea  mov     rbx, [rbp+Binding]
0x18000bbee  lea     r9, [rbp+var_8]
0x18000bbf2  mov     r8, rdi
0x18000bbf5  mov     [rbp+Binding], rbx
0x18000bbf9  lea     rdx, [rbp+Binding]
0x18000bbfd  call    ??$InvokeStubFunction@P6AJPEAXU_GUID@@PEBG@ZPEAXAEAU1@AEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAXU_GUID@@PEBG@Z$$QEAPEAXAEAU3@AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,ushort const *),void *,_GUID &,ushort const * &>(long (*)(void *,_GUID,ushort const *),void * &&,_GUID &,ushort const * &)
0x18000bc02  mov     edi, eax
0x18000bc04  test    eax, eax
0x18000bc06  jns     short loc_18000BC37
0x18000bc08  mov     rcx, [rbp+8]; this
0x18000bc0c  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bc13  mov     r9d, eax; char *
0x18000bc16  mov     edx, 287h; void *
0x18000bc1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc20  test    rbx, rbx
0x18000bc23  jz      short loc_18000BC33
0x18000bc25  lea     rcx, [rbp+var_8]; Binding
0x18000bc29  mov     [rbp+var_8], rbx
0x18000bc2d  call    cs:__imp_RpcBindingFree
0x18000bc33  mov     eax, edi
0x18000bc35  jmp     short loc_18000BC4C
0x18000bc37  test    rbx, rbx
0x18000bc3a  jz      short loc_18000BC4A
0x18000bc3c  lea     rcx, [rbp+var_8]; Binding
0x18000bc40  mov     [rbp+var_8], rbx
0x18000bc44  call    cs:__imp_RpcBindingFree
0x18000bc4a  xor     eax, eax
0x18000bc4c  mov     rbx, [rsp+30h+arg_10]
0x18000bc51  mov     rdi, [rsp+30h+arg_18]
0x18000bc56  add     rsp, 30h
0x18000bc5a  pop     rbp
0x18000bc5b  retn
```
