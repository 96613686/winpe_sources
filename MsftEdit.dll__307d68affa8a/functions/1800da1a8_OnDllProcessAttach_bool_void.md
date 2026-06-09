# OnDllProcessAttach(bool,void *)

- ea: `0x1800da1a8`
- end: `0x1800da277`
- name: `?OnDllProcessAttach@@YAH_NPEAX@Z`
- size: `207`
- prototype: `int(bool, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180120754`

## callees

- `0x18002af88`
- `0x1800da1a8`
- `0x180106314`
- `0x18010ac24`
- `0x18010d5f0`
- `0x18013ee24`
- `0x1801f3dd8`
- `0x1801f4380`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800da21d`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800da21d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800da201`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800da214`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800da201`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800da214`

## pseudocode

```c
__int64 __fastcall OnDllProcessAttach(__int64 a1, HMODULE a2)
{
  RichEdit::RichEditCoreAPIs *v3; // rcx
  RTL_SRWLOCK *Lock; // rax
  RTL_SRWLOCK *v6; // rax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRicheditCore>::GetImpl'::`2'::impl)
    && (RichEdit::RichEditCoreAPIs::Initialize(v3), byte_1802DF828) )
  {
    if ( qword_1802DF8F0 )
      return (unsigned __int8)qword_1802DF8F0();
  }
  else
  {
    CLockSharedData::LockOwner = 0;
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    InitializeSRWLock(Lock);
    v6 = (RTL_SRWLOCK *)CLockSharedOS::GetLock(1);
    InitializeSRWLock(v6);
    DisableThreadLibraryCalls(a2);
    hinstRE = a2;
    if ( IClipboard::Create() )
    {
      wcscpy(&ClassName, L"RICHEDIT50W");
      if ( !(unsigned __int8)IsRegisterClassWPresent() || (unsigned int)RichFRegisterClass() )
      {
        McGenEventRegister_EventRegister();
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800da1a8  push    rbx
0x1800da1aa  sub     rsp, 20h
0x1800da1ae  mov     rbx, rdx
0x1800da1b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRicheditCore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRicheditCore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore> `wil::Feature<__WilFeatureTraits_Feature_EnableRicheditCore>::GetImpl(void)'::`2'::impl
0x1800da1b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRicheditCore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore>::__private_IsEnabled(void)
0x1800da1bd  test    al, al
0x1800da1bf  jz      short loc_1800DA1EC
0x1800da1c1  call    ?Initialize@RichEditCoreAPIs@RichEdit@@YAXXZ; RichEdit::RichEditCoreAPIs::Initialize(void)
0x1800da1c6  cmp     cs:byte_1802DF828, 0
0x1800da1cd  jz      short loc_1800DA1EC
0x1800da1cf  mov     rax, cs:qword_1802DF8F0
0x1800da1d6  test    rax, rax
0x1800da1d9  jz      loc_1800DA26F
0x1800da1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da1e4  movzx   eax, al
0x1800da1e7  jmp     loc_1800DA271
0x1800da1ec  xor     ecx, ecx
0x1800da1ee  mov     cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x1800da1f9  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800da1fe  mov     rcx, rax; SRWLock
0x1800da201  call    cs:__imp_InitializeSRWLock
0x1800da207  mov     ecx, 1
0x1800da20c  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800da211  mov     rcx, rax; SRWLock
0x1800da214  call    cs:__imp_InitializeSRWLock
0x1800da21a  mov     rcx, rbx; hLibModule
0x1800da21d  call    cs:__imp_DisableThreadLibraryCalls
0x1800da223  mov     cs:?hinstRE@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hinstRE
0x1800da22a  call    ?Create@IClipboard@@SA_NXZ; IClipboard::Create(void)
0x1800da22f  test    al, al
0x1800da231  jz      short loc_1800DA26F
0x1800da233  movups  xmm0, xmmword ptr cs:aRichedit50w; "RICHEDIT50W"
0x1800da23a  movsd   xmm1, qword ptr cs:aRichedit50w+10h; "50W"
0x1800da242  movups  cs:ClassName, xmm0
0x1800da249  movsd   cs:qword_1802DF1A0, xmm1
0x1800da251  call    IsRegisterClassWPresent
0x1800da256  test    al, al
0x1800da258  jz      short loc_1800DA263
0x1800da25a  call    RichFRegisterClass
0x1800da25f  test    eax, eax
0x1800da261  jz      short loc_1800DA26F
0x1800da263  call    McGenEventRegister_EventRegister
0x1800da268  mov     eax, 1
0x1800da26d  jmp     short loc_1800DA271
0x1800da26f  xor     eax, eax
0x1800da271  add     rsp, 20h
0x1800da275  pop     rbx
0x1800da276  retn
```
