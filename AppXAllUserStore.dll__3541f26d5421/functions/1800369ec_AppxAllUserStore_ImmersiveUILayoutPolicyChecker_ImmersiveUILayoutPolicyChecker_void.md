# AppxAllUserStore::ImmersiveUILayoutPolicyChecker::~ImmersiveUILayoutPolicyChecker(void)

- ea: `0x1800369ec`
- end: `0x180036a53`
- name: `??1ImmersiveUILayoutPolicyChecker@AppxAllUserStore@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(void (**this)(void))`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800110cc`

## callees

- `0x1800369ec`
- `0x180036bb0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180036a11`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180036a11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a4c`

## string_xrefs

- `0x180036a1c`: `Could not unload handle to module iuilp.dll`

## pseudocode

```c
void __fastcall AppxAllUserStore::ImmersiveUILayoutPolicyChecker::~ImmersiveUILayoutPolicyChecker(void (**this)(void))
{
  HMODULE v2; // rcx
  unsigned int v3; // eax
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( this[6] )
    this[10]();
  v2 = (HMODULE)this[5];
  if ( v2 )
  {
    v3 = FreeLibrary(v2);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\immersiveuilayoutpolicychecker.cpp",
      (const char *)v3,
      (int)"Could not unload handle to module iuilp.dll",
      v4);
    this[5] = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800369ec  push    rbx
0x1800369ee  sub     rsp, 30h
0x1800369f2  mov     rbx, rcx
0x1800369f5  add     rcx, 30h ; '0'
0x1800369f9  cmp     qword ptr [rcx], 0
0x1800369fd  jz      short loc_180036A08
0x1800369ff  mov     rax, [rbx+50h]
0x180036a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a08  mov     rcx, [rbx+28h]; hLibModule
0x180036a0c  test    rcx, rcx
0x180036a0f  jz      short loc_180036A44
0x180036a11  call    cs:__imp_FreeLibrary
0x180036a17  mov     rcx, [rsp+38h]; this
0x180036a1c  lea     rdx, aCouldNotUnload; "Could not unload handle to module iuilp"...
0x180036a23  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180036a28  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\appxalluserst"...
0x180036a2f  mov     edx, 84h; void *
0x180036a34  mov     r9d, eax; char *
0x180036a37  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180036a3c  mov     qword ptr [rbx+28h], 0
0x180036a44  mov     rcx, rbx
0x180036a47  add     rsp, 30h
0x180036a4b  pop     rbx
0x180036a4c  jmp     cs:__imp_DeleteCriticalSection
```
