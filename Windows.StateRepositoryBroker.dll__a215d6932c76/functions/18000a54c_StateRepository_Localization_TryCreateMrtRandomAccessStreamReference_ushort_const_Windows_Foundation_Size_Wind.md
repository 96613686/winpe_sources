# StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(ushort const *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x18000a54c`
- end: `0x18000a615`
- name: `?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEBGUSize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@5@@Z`
- size: `201`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a510`

## callees

- `0x180006224`
- `0x180009900`
- `0x180009af8`
- `0x18000a1b8`
- `0x18000a54c`

## string_xrefs

- `0x18000a56a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x18000a5e6`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(
        unsigned __int16 *a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int MrtRandomAccessStreamReferencePath; // eax
  __int64 v5; // rdx
  __int64 v6; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PCWSTR sourceString; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    *a3 = 0;
    sourceString = 0;
    MrtRandomAccessStreamReferencePath = GetMrtRandomAccessStreamReferencePath(a1, a2, (__int64 *)&sourceString);
    v3 = MrtRandomAccessStreamReferencePath;
    if ( MrtRandomAccessStreamReferencePath >= 0 )
    {
      if ( !sourceString )
        goto LABEL_14;
      v6 = -1;
      do
        ++v6;
      while ( sourceString[v6] );
      if ( !v6
        || (MrtRandomAccessStreamReferencePath = CreateMrtRandomAccessStreamReferenceInternal(sourceString),
            v3 = MrtRandomAccessStreamReferencePath,
            MrtRandomAccessStreamReferencePath >= 0)
        || MrtRandomAccessStreamReferencePath == -2147024809
        || MrtRandomAccessStreamReferencePath == -2147024894 )
      {
LABEL_14:
        v3 = 0;
        goto LABEL_15;
      }
      v5 = 228;
    }
    else
    {
      v5 = 220;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
      (const char *)(unsigned int)MrtRandomAccessStreamReferencePath,
      v8);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
    return v3;
  }
  v3 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
    (const char *)0x80004003LL,
    v8);
  return v3;
}

```

## disassembly

```asm
0x18000a54c  mov     [rsp+arg_0], rbx
0x18000a551  mov     [rsp+arg_8], rsi
0x18000a556  push    rdi; int
0x18000a557  sub     rsp, 20h
0x18000a55b  xor     esi, esi
0x18000a55d  mov     rdi, r8
0x18000a560  test    r8, r8
0x18000a563  jnz     short loc_18000A585
0x18000a565  mov     rcx, [rsp+28h]; this
0x18000a56a  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000a571  mov     ebx, 80004003h
0x18000a576  mov     edx, 0D8h; void *
0x18000a57b  mov     r9d, ebx; char *
0x18000a57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a583  jmp     short loc_18000A603
0x18000a585  mov     [r8], rsi
0x18000a588  lea     r8, [rsp+28h+sourceString]
0x18000a58d  mov     [rsp+28h+sourceString], rsi
0x18000a592  call    GetMrtRandomAccessStreamReferencePath
0x18000a597  mov     ebx, eax
0x18000a599  test    eax, eax
0x18000a59b  jns     short loc_18000A5A4
0x18000a59d  mov     edx, 0DCh
0x18000a5a2  jmp     short loc_18000A5E1
0x18000a5a4  mov     rcx, [rsp+28h+sourceString]; sourceString
0x18000a5a9  test    rcx, rcx
0x18000a5ac  jz      short loc_18000A5F7
0x18000a5ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a5b2  inc     rax
0x18000a5b5  cmp     [rcx+rax*2], si
0x18000a5b9  jnz     short loc_18000A5B2
0x18000a5bb  test    rax, rax
0x18000a5be  jz      short loc_18000A5F7
0x18000a5c0  mov     rdx, rdi
0x18000a5c3  call    CreateMrtRandomAccessStreamReferenceInternal
0x18000a5c8  mov     ebx, eax
0x18000a5ca  test    eax, eax
0x18000a5cc  jns     short loc_18000A5F7
0x18000a5ce  cmp     eax, 80070057h
0x18000a5d3  jz      short loc_18000A5F7
0x18000a5d5  cmp     eax, 80070002h
0x18000a5da  jz      short loc_18000A5F7
0x18000a5dc  mov     edx, 0E4h; void *
0x18000a5e1  mov     rcx, [rsp+28h]; this
0x18000a5e6  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000a5ed  mov     r9d, eax; char *
0x18000a5f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5f5  jmp     short loc_18000A5F9
0x18000a5f7  mov     ebx, esi
0x18000a5f9  lea     rcx, [rsp+28h+sourceString]
0x18000a5fe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a603  mov     rsi, [rsp+28h+arg_8]
0x18000a608  mov     eax, ebx
0x18000a60a  mov     rbx, [rsp+28h+arg_0]
0x18000a60f  add     rsp, 20h
0x18000a613  pop     rdi
0x18000a614  retn
```
