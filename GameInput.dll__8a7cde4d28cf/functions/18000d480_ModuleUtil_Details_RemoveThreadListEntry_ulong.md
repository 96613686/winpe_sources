# ModuleUtil::Details::RemoveThreadListEntry(ulong)

- ea: `0x18000d480`
- end: `0x18000d566`
- name: `?RemoveThreadListEntry@Details@ModuleUtil@@YA_NK@Z`
- size: `230`
- prototype: `bool __fastcall(ModuleUtil::Details *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c568`

## callees

- `0x180001008`
- `0x18000c11c`
- `0x18000d480`

## string_xrefs

- `0x18000d51d`: `onecore\xbox\gameinput\common\GameInputModuleUtil.cpp`
- `0x18000d505`: `Thread list entry missing`

## pseudocode

```c
char __fastcall ModuleUtil::Details::RemoveThreadListEntry(ModuleUtil::Details *this, __int64 a2, __int64 a3, int a4)
{
  int v4; // r8d
  __int64 *v5; // rdx
  __int64 *i; // rcx
  __int64 v7; // rax
  __int64 **v8; // r8
  int v10; // [rsp+50h] [rbp+8h] BYREF
  int v11; // [rsp+58h] [rbp+10h] BYREF
  const char *v12; // [rsp+60h] [rbp+18h] BYREF
  const char *v13; // [rsp+68h] [rbp+20h] BYREF

  v4 = (int)this;
  v5 = &qword_180069920[3 * ((unsigned __int8)this & 7)];
  for ( i = (__int64 *)*v5; i != v5; i = (__int64 *)*i )
  {
    v7 = *i;
    if ( *((_DWORD *)i + 4) == v4 )
    {
      if ( *(__int64 **)(v7 + 8) != i || (v8 = (__int64 **)i[1], *v8 != i) )
        __fastfail(3u);
      *v8 = (__int64 *)v7;
      *(_QWORD *)(v7 + 8) = v8;
      --*((_DWORD *)v5 + 4);
      operator delete(i, (const struct std::nothrow_t *)v5);
      return 1;
    }
  }
  if ( (unsigned int)dword_180069000 > 3 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
  {
    v10 = v4;
    v12 = "Thread list entry missing";
    v11 = 86;
    v13 = "onecore\\xbox\\gameinput\\common\\GameInputModuleUtil.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)&word_18005A026,
      v4,
      a4,
      (__int64)&v13,
      (__int64)&v11,
      (__int64)&v12,
      (__int64)&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d480  sub     rsp, 48h
0x18000d484  mov     eax, ecx
0x18000d486  mov     r8d, ecx
0x18000d489  lea     rcx, qword_180069920
0x18000d490  and     eax, 7
0x18000d493  lea     rax, [rax+rax*2]
0x18000d497  lea     rdx, [rcx+rax*8]; struct std::nothrow_t *
0x18000d49b  mov     rcx, [rdx]; P
0x18000d49e  cmp     rcx, rdx
0x18000d4a1  jz      short loc_18000D4DD
0x18000d4a3  mov     rax, [rcx]
0x18000d4a6  cmp     [rcx+10h], r8d
0x18000d4aa  jz      short loc_18000D4B1
0x18000d4ac  mov     rcx, rax
0x18000d4af  jmp     short loc_18000D49E
0x18000d4b1  cmp     [rax+8], rcx
0x18000d4b5  jnz     short loc_18000D4D6
0x18000d4b7  mov     r8, [rcx+8]
0x18000d4bb  cmp     [r8], rcx
0x18000d4be  jnz     short loc_18000D4D6
0x18000d4c0  mov     [r8], rax
0x18000d4c3  mov     [rax+8], r8
0x18000d4c7  dec     dword ptr [rdx+10h]
0x18000d4ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d4cf  mov     al, 1
0x18000d4d1  jmp     loc_18000D560
0x18000d4d6  mov     ecx, 3
0x18000d4db  int     29h; Win8: RtlFailFast(ecx)
0x18000d4dd  mov     eax, cs:dword_180069000
0x18000d4e3  cmp     eax, 3
0x18000d4e6  jbe     short loc_18000D55E
0x18000d4e8  mov     rcx, cs:qword_180069018
0x18000d4ef  mov     rax, cs:qword_180069010
0x18000d4f6  test    al, 2
0x18000d4f8  jz      short loc_18000D55E
0x18000d4fa  mov     rax, rcx
0x18000d4fd  and     eax, 2
0x18000d500  cmp     rax, rcx
0x18000d503  jnz     short loc_18000D55E
0x18000d505  lea     rax, aThreadListEntr; "Thread list entry missing"
0x18000d50c  mov     [rsp+48h+arg_0], r8d
0x18000d511  mov     [rsp+48h+arg_10], rax
0x18000d516  lea     rdx, word_18005A026
0x18000d51d  lea     rax, aOnecoreXboxGam_29; "onecore\\xbox\\gameinput\\common\\GameI"...
0x18000d524  mov     [rsp+48h+arg_8], 56h ; 'V'
0x18000d52c  mov     [rsp+48h+arg_18], rax
0x18000d531  lea     rax, [rsp+48h+arg_0]
0x18000d536  mov     [rsp+48h+var_10], rax
0x18000d53b  lea     rax, [rsp+48h+arg_10]
0x18000d540  mov     [rsp+48h+var_18], rax
0x18000d545  lea     rax, [rsp+48h+arg_8]
0x18000d54a  mov     [rsp+48h+var_20], rax
0x18000d54f  lea     rax, [rsp+48h+arg_18]
0x18000d554  mov     [rsp+48h+var_28], rax
0x18000d559  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000d55e  xor     al, al
0x18000d560  add     rsp, 48h
0x18000d564  retn
```
