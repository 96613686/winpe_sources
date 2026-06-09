# FrameProvider::Init(void)

- ea: `0x18002ba08`
- end: `0x18002ba98`
- name: `?Init@FrameProvider@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ea10`

## callees

- `0x18002ac58`
- `0x18002ad88`
- `0x18002ba08`
- `0x18002c4fc`
- `0x18002c5fc`

## import_xrefs

- `DUI70!InitProcessPriv` at `0x18002ba2c`
- `DUI70!InitProcessPriv` at `0x18002ba2c`
- `DUI70!InitThread` at `0x18002ba3d`
- `DUI70!InitThread` at `0x18002ba3d`
- `DUI70!UnInitProcessPriv` at `0x18002ba50`
- `DUI70!UnInitProcessPriv` at `0x18002ba50`

## pseudocode

```c
__int64 __fastcall FrameProvider::Init(FrameProvider *this, __int64 a2, __int64 a3)
{
  int inited; // ebx

  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(2);
    if ( inited < 0 )
      UnInitProcessPriv(&_ImageBase);
  }
  *((_DWORD *)this + 154) = inited;
  if ( inited >= 0 )
  {
    inited = -2147467259;
    if ( (int)DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register() >= 0
      && (int)CElementWithSite::Register() >= 0
      && (int)DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register() >= 0
      && (int)DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register() >= 0 )
    {
      return 0;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002ba08  mov     [rsp+arg_0], rbx
0x18002ba0d  push    rdi
0x18002ba0e  sub     rsp, 30h
0x18002ba12  mov     r9b, 1
0x18002ba15  mov     [rsp+38h+var_18], 1
0x18002ba1a  mov     rdi, rcx
0x18002ba1d  lea     rdx, __ImageBase
0x18002ba24  mov     r8b, r9b
0x18002ba27  mov     ecx, 0Eh
0x18002ba2c  call    cs:__imp_InitProcessPriv
0x18002ba32  mov     ebx, eax
0x18002ba34  test    eax, eax
0x18002ba36  js      short loc_18002BA56
0x18002ba38  mov     ecx, 2
0x18002ba3d  call    cs:__imp_InitThread
0x18002ba43  mov     ebx, eax
0x18002ba45  test    eax, eax
0x18002ba47  jns     short loc_18002BA56
0x18002ba49  lea     rcx, __ImageBase
0x18002ba50  call    cs:__imp_UnInitProcessPriv
0x18002ba56  mov     [rdi+268h], ebx
0x18002ba5c  test    ebx, ebx
0x18002ba5e  js      short loc_18002BA8B
0x18002ba60  mov     ebx, 80004005h
0x18002ba65  call    ?Register@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002ba6a  test    eax, eax
0x18002ba6c  js      short loc_18002BA8B
0x18002ba6e  call    ?Register@CElementWithSite@@SAJXZ; CElementWithSite::Register(void)
0x18002ba73  test    eax, eax
0x18002ba75  js      short loc_18002BA8B
0x18002ba77  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002ba7c  test    eax, eax
0x18002ba7e  js      short loc_18002BA8B
0x18002ba80  call    ?Register@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002ba85  test    eax, eax
0x18002ba87  js      short loc_18002BA8B
0x18002ba89  xor     ebx, ebx
0x18002ba8b  mov     eax, ebx
0x18002ba8d  mov     rbx, [rsp+38h+arg_0]
0x18002ba92  add     rsp, 30h
0x18002ba96  pop     rdi
0x18002ba97  retn
```
