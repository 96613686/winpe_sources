# IsFileNewerThan(ushort const *,ushort const *)

- ea: `0x140002798`
- end: `0x140002880`
- name: `?IsFileNewerThan@@YAJPEBG0@Z`
- size: `232`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e5c`
- `0x140002ac0`

## callees

- `0x140001008`
- `0x140002340`
- `0x140002798`

## pseudocode

```c
__int64 __fastcall IsFileNewerThan(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int FileVersion; // ebx
  int v4; // r9d
  const char *v6; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v7; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int64 v8; // [rsp+78h] [rbp+28h] BYREF

  v8 = 0;
  FileVersion = GetFileVersion(a1);
  if ( FileVersion >= 0 )
  {
    v7 = 0;
    GetFileVersion(a2);
    return (v7 & 0xFFFFFFFFFFFF0000uLL) != 0xA000047BA0000LL && v8 <= v7;
  }
  else
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      LODWORD(v7) = FileVersion;
      v6 = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
      LODWORD(v8) = 57;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (unsigned int)byte_14000A789,
        2048,
        v4,
        (__int64)&v6,
        (__int64)&v8,
        (__int64)&v7);
    }
    return (unsigned int)FileVersion;
  }
}

```

## disassembly

```asm
0x140002798  mov     [rsp-8+arg_0], rbx
0x14000279d  mov     [rsp-8+arg_8], rdi
0x1400027a2  push    rbp
0x1400027a3  mov     rbp, rsp
0x1400027a6  sub     rsp, 50h
0x1400027aa  mov     rdi, rdx
0x1400027ad  mov     [rbp+arg_18], 0
0x1400027b5  lea     rdx, [rbp+arg_18]
0x1400027b9  call    GetFileVersion
0x1400027be  mov     ebx, eax
0x1400027c0  test    eax, eax
0x1400027c2  jns     short loc_140002833
0x1400027c4  mov     ecx, cs:dword_14000E000
0x1400027ca  cmp     ecx, 2
0x1400027cd  jbe     short loc_14000282F
0x1400027cf  mov     rdx, cs:qword_14000E018
0x1400027d6  mov     r8d, 800h
0x1400027dc  mov     rcx, cs:qword_14000E010
0x1400027e3  test    r8, rcx
0x1400027e6  jz      short loc_14000282F
0x1400027e8  mov     rax, rdx
0x1400027eb  and     rax, r8
0x1400027ee  cmp     rax, rdx
0x1400027f1  jnz     short loc_14000282F
0x1400027f3  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400027fa  mov     dword ptr [rbp+arg_10], ebx
0x1400027fd  mov     [rbp+var_10], rax
0x140002801  lea     rdx, byte_14000A789
0x140002808  lea     rax, [rbp+arg_10]
0x14000280c  mov     dword ptr [rbp+arg_18], 39h ; '9'
0x140002813  mov     [rsp+50h+var_20], rax
0x140002818  lea     rax, [rbp+arg_18]
0x14000281c  mov     [rsp+50h+var_28], rax
0x140002821  lea     rax, [rbp+var_10]
0x140002825  mov     [rsp+50h+var_30], rax
0x14000282a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000282f  mov     eax, ebx
0x140002831  jmp     short loc_140002870
0x140002833  lea     rdx, [rbp+arg_10]
0x140002837  mov     [rbp+arg_10], 0
0x14000283f  mov     rcx, rdi; lptstrFilename
0x140002842  call    GetFileVersion
0x140002847  mov     rcx, [rbp+arg_10]
0x14000284b  mov     rdx, 0A000047BA0000h
0x140002855  mov     rax, rcx
0x140002858  and     rax, 0FFFFFFFFFFFF0000h
0x14000285e  cmp     rax, rdx
0x140002861  jz      short loc_14000286E
0x140002863  xor     eax, eax
0x140002865  cmp     [rbp+arg_18], rcx
0x140002869  setbe   al
0x14000286c  jmp     short loc_140002870
0x14000286e  xor     eax, eax
0x140002870  mov     rbx, [rsp+50h+arg_0]
0x140002875  mov     rdi, [rsp+50h+arg_8]
0x14000287a  add     rsp, 50h
0x14000287e  pop     rbp
0x14000287f  retn
```
