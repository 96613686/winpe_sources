# Windows::UI::Input::InjectionBrokerImpl::InjectTouchInput(unsigned __int64,uint,Windows::UI::Input::PointerTouchInfo * const)

- ea: `0x180006dd0`
- end: `0x180006de0`
- name: `?InjectTouchInput@InjectionBrokerImpl@Input@UI@Windows@@UEAAJ_KIQEAUPointerTouchInfo@234@@Z`
- size: `16`
- prototype: `__int64 __fastcall(Windows::UI::Input::InjectionBrokerImpl *this, Windows::UI::Input::Common *, unsigned int, struct Windows::UI::Input::PointerTouchInfo *const)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ef04`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::InjectTouchInput(
        Windows::UI::Input::InjectionBrokerImpl *this,
        Windows::UI::Input::Common *a2,
        unsigned int a3,
        struct Windows::UI::Input::PointerTouchInfo *const a4)
{
  return Windows::UI::Input::Common::InjectTouchInput(a2, a3, (unsigned int)a4, a4);
}

```

## disassembly

```asm
0x180006dd0  mov     eax, r8d
0x180006dd3  mov     rcx, rdx; this
0x180006dd6  mov     edx, eax; unsigned __int64
0x180006dd8  mov     r8, r9; unsigned int
0x180006ddb  jmp     ?InjectTouchInput@Common@Input@UI@Windows@@YAJ_KIQEAUPointerTouchInfo@234@@Z; Windows::UI::Input::Common::InjectTouchInput(unsigned __int64,uint,Windows::UI::Input::PointerTouchInfo * const)
```
