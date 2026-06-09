# _DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18000d56c`
- end: `0x18000d651`
- name: `?_DllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, ModuleUtil *this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d9b0`

## callees

- `0x180001304`
- `0x18000389c`
- `0x18000c568`
- `0x18000cc28`
- `0x18000d56c`
- `0x18000d7a4`
- `0x18000d870`

## string_xrefs

- `0x18000d5da`: `onecore\xbox\gameinput\common\DllMain.cpp`

## pseudocode

```c
__int64 __fastcall _DllMain(HINSTANCE hinstDLL, ModuleUtil *this, void *a3)
{
  DWORD v3; // ebx
  ModuleUtil *v5; // rcx
  int v7; // edx
  int v8; // r9d
  unsigned int v9; // edi
  int v10; // [rsp+58h] [rbp+10h] BYREF
  void *v11; // [rsp+60h] [rbp+18h] BYREF
  const char *v12; // [rsp+68h] [rbp+20h] BYREF

  v11 = a3;
  v3 = (unsigned int)this;
  if ( (_DWORD)this == 1 )
  {
    if ( (int)GameInputInitialize() < 0 )
      return 0;
    if ( !byte_180069913 )
    {
      v7 = ModuleUtil::Initialize(v5);
      if ( v7 < 0 && (unsigned int)dword_180069000 > 2 )
      {
        a3 = (void *)qword_180069018;
        if ( (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
        {
          v10 = v7;
          v12 = "onecore\\xbox\\gameinput\\common\\DllMain.cpp";
          LODWORD(v11) = 43;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&word_180059F16,
            qword_180069018,
            v8,
            (__int64)&v12,
            (__int64)&v11,
            (__int64)&v10);
        }
      }
    }
  }
  else if ( !byte_180069913 )
  {
    ModuleUtil::DispatchCallbacks((ModuleUtil *)(unsigned int)this);
  }
  v9 = DllMain(hinstDLL, v3, a3);
  if ( !v3 )
    GameInputUninitialize();
  return v9;
}

```

## disassembly

```asm
0x18000d56c  mov     [rsp+arg_0], rbx
0x18000d571  mov     [rsp+arg_10], r8
0x18000d576  push    rdi
0x18000d577  sub     rsp, 40h
0x18000d57b  mov     ebx, edx
0x18000d57d  mov     rdi, rcx
0x18000d580  cmp     edx, 1
0x18000d583  jnz     loc_18000D61E
0x18000d589  call    GameInputInitialize
0x18000d58e  test    eax, eax
0x18000d590  jns     short loc_18000D599
0x18000d592  xor     eax, eax
0x18000d594  jmp     loc_18000D645
0x18000d599  cmp     cs:byte_180069913, 0
0x18000d5a0  jnz     loc_18000D62E
0x18000d5a6  call    ?Initialize@ModuleUtil@@YAJXZ; ModuleUtil::Initialize(void)
0x18000d5ab  mov     edx, eax
0x18000d5ad  test    eax, eax
0x18000d5af  jns     short loc_18000D62E
0x18000d5b1  mov     ecx, cs:dword_180069000
0x18000d5b7  cmp     ecx, 2
0x18000d5ba  jbe     short loc_18000D62E
0x18000d5bc  mov     r8, cs:qword_180069018
0x18000d5c3  mov     rcx, cs:qword_180069010
0x18000d5ca  test    cl, 2
0x18000d5cd  jz      short loc_18000D62E
0x18000d5cf  mov     rax, r8
0x18000d5d2  and     eax, 2
0x18000d5d5  cmp     rax, r8
0x18000d5d8  jnz     short loc_18000D62E
0x18000d5da  lea     rax, aOnecoreXboxGam_23; "onecore\\xbox\\gameinput\\common\\DllMa"...
0x18000d5e1  mov     [rsp+48h+arg_8], edx
0x18000d5e5  mov     [rsp+48h+arg_18], rax
0x18000d5ea  lea     rdx, word_180059F16
0x18000d5f1  lea     rax, [rsp+48h+arg_8]
0x18000d5f6  mov     dword ptr [rsp+48h+arg_10], 2Bh ; '+'
0x18000d5fe  mov     [rsp+48h+var_18], rax
0x18000d603  lea     rax, [rsp+48h+arg_10]
0x18000d608  mov     [rsp+48h+var_20], rax
0x18000d60d  lea     rax, [rsp+48h+arg_18]
0x18000d612  mov     [rsp+48h+var_28], rax
0x18000d617  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d61c  jmp     short loc_18000D62E
0x18000d61e  cmp     cs:byte_180069913, 0
0x18000d625  jnz     short loc_18000D62E
0x18000d627  mov     ecx, ebx; this
0x18000d629  call    ?DispatchCallbacks@ModuleUtil@@YAXK@Z; ModuleUtil::DispatchCallbacks(ulong)
0x18000d62e  mov     edx, ebx; fdwReason
0x18000d630  mov     rcx, rdi; hinstDLL
0x18000d633  call    DllMain
0x18000d638  mov     edi, eax
0x18000d63a  test    ebx, ebx
0x18000d63c  jnz     short loc_18000D643
0x18000d63e  call    GameInputUninitialize
0x18000d643  mov     eax, edi
0x18000d645  mov     rbx, [rsp+48h+arg_0]
0x18000d64a  add     rsp, 40h
0x18000d64e  pop     rdi
0x18000d64f  retn
```
