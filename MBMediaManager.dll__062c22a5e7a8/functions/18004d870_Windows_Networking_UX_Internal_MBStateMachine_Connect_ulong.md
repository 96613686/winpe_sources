# Windows::Networking::UX::Internal::MBStateMachine::Connect(ulong *)

- ea: `0x18004d870`
- end: `0x18004d960`
- name: `?Connect@MBStateMachine@Internal@UX@Networking@Windows@@UEAAJPEAK@Z`
- size: `240`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBStateMachine *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000ad20`
- `0x18000fe58`
- `0x180017ac4`
- `0x18001bd80`
- `0x18004d870`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004d8ad`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004d8ad`
- `ext-ms-win-wwan-wwapi-l1-1-2!WwanConnect` at `0x18004d8ee`
- `ext-ms-win-wwan-wwapi-l1-1-2!WwanConnect` at `0x18004d8ee`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBStateMachine::Connect(
        Windows::Networking::UX::Internal::MBStateMachine *this,
        unsigned int *a2)
{
  int v4; // eax
  signed int v5; // ebx
  int v6; // eax
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-38h]
  _QWORD v10[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int16 v12; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v10[0] = -1;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(v10);
  v4 = WwanOpenHandle(1, 0, &v13, v10);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    v7 = 216;
    goto LABEL_10;
  }
  v12 = 0;
  v9 = (int)a2;
  v6 = WwanConnect(v10[0], (char *)this + 40, 2, &v12);
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( v5 < 0 )
  {
    v7 = 207;
LABEL_10:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\statemachine\\lib\\mbstatemachine.cpp",
      (const char *)(unsigned int)v5,
      v9);
    goto LABEL_11;
  }
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBStateMachine::Connect",
    211,
    "WwanConnect succeeded. ulRequestId=%d",
    *a2);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004d870  mov     rax, rsp
0x18004d873  mov     [rax+8], rbx
0x18004d877  mov     [rax+10h], rsi
0x18004d87b  push    rdi
0x18004d87c  sub     rsp, 50h
0x18004d880  mov     rdi, rdx
0x18004d883  mov     dword ptr [rax+20h], 0
0x18004d88a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004d88e  mov     rsi, rcx
0x18004d891  lea     rcx, [rax-18h]
0x18004d895  mov     [rax-18h], rdx
0x18004d899  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18004d89e  xor     edx, edx
0x18004d8a0  lea     r9, [rsp+58h+var_18]
0x18004d8a5  lea     r8, [rsp+58h+arg_18]
0x18004d8aa  lea     ecx, [rdx+1]
0x18004d8ad  call    cs:__imp_WwanOpenHandle
0x18004d8b3  mov     ebx, eax
0x18004d8b5  test    eax, eax
0x18004d8b7  jle     short loc_18004D8C2
0x18004d8b9  movzx   ebx, ax
0x18004d8bc  or      ebx, 80070000h
0x18004d8c2  test    ebx, ebx
0x18004d8c4  js      short loc_18004D92B
0x18004d8c6  mov     rcx, [rsp+58h+var_18]
0x18004d8cb  lea     rdx, [rsi+28h]
0x18004d8cf  xor     eax, eax
0x18004d8d1  lea     r9, [rsp+58h+arg_10]
0x18004d8d6  mov     [rsp+58h+var_28], rax
0x18004d8db  mov     [rsp+58h+var_30], rax
0x18004d8e0  mov     [rsp+58h+arg_10], ax
0x18004d8e5  lea     r8d, [rax+2]
0x18004d8e9  mov     [rsp+58h+var_38], rdi
0x18004d8ee  call    cs:__imp_WwanConnect
0x18004d8f4  mov     ebx, eax
0x18004d8f6  test    eax, eax
0x18004d8f8  jle     short loc_18004D903
0x18004d8fa  movzx   ebx, ax
0x18004d8fd  or      ebx, 80070000h
0x18004d903  test    ebx, ebx
0x18004d905  jns     short loc_18004D90E
0x18004d907  mov     edx, 0CFh
0x18004d90c  jmp     short loc_18004D930
0x18004d90e  mov     r9d, [rdi]
0x18004d911  lea     r8, aWwanconnectSuc; "WwanConnect succeeded. ulRequestId=%d"
0x18004d918  mov     edx, 0D3h; unsigned int
0x18004d91d  lea     rcx, aWindowsNetwork_2; "Windows::Networking::UX::Internal::MBSt"...
0x18004d924  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004d929  jmp     short loc_18004D944
0x18004d92b  mov     edx, 0D8h; void *
0x18004d930  mov     rcx, [rsp+58h]; this
0x18004d935  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mbmediamanager\\st"...
0x18004d93c  mov     r9d, ebx; char *
0x18004d93f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004d944  lea     rcx, [rsp+58h+var_18]
0x18004d949  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18004d94e  mov     rsi, [rsp+58h+arg_8]
0x18004d953  mov     eax, ebx
0x18004d955  mov     rbx, [rsp+58h+arg_0]
0x18004d95a  add     rsp, 50h
0x18004d95e  pop     rdi
0x18004d95f  retn
```
