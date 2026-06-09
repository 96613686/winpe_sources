# Gfx::DestroyResourceCaches(ARC::IFactory &)

- ea: `0x1800a0c40`
- end: `0x1800a0d4e`
- name: `?DestroyResourceCaches@Gfx@@YAXAEAUIFactory@ARC@@@Z`
- size: `270`
- prototype: `void __fastcall(Gfx *__hidden this, struct ARC::IFactory *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800573f0`
- `0x1800a0c40`
- `0x1800a0d50`
- `0x1800a0e70`
- `0x1800a0ef4`

## import_xrefs

- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x1800a0c89`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x1800a0c89`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x1800a0d1d`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x1800a0d1d`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1800a0d28`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1800a0d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Gfx::DestroyResourceCaches(Gfx *this, struct ARC::IFactory *a2)
{
  const struct ARC::IFactory *v2; // rdi
  const struct ARC::IFactory *v3; // rdx
  Gfx *v4; // rbx
  struct ARC::IDevice *v5; // rdx
  struct ARC::IDeviceContext *v6; // rdx
  const ARC::Exception *v7; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v8[88]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v12; // [rsp+B8h] [rbp+10h] BYREF
  Gfx *v13; // [rsp+C0h] [rbp+18h]

  v2 = this;
  if ( !(*(unsigned __int8 (__fastcall **)(Gfx *, struct ARC::IFactory *))(*(_QWORD *)this + 192LL))(this, a2) )
  {
    ARC::ExceptionScope::ExceptionScope((ARC::ExceptionScope *)v8, v2);
    try
    {
      while ( 2 )
      {
        try
        {
          v4 = *(Gfx **)(*(__int64 (__fastcall **)(const struct ARC::IFactory *, __int64 *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v2 + 176LL))(
                          v2,
                          &v12,
                          0xFFFFFFFFLL,
                          0,
                          0,
                          0);
          v13 = v4;
          (**(void (__fastcall ***)(Gfx *))v4)(v4);
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
          Gfx::DestroyResourceCaches(v4, v5);
          Gfx::DestroyModel3DCacheOnDeviceRelease(v4, v6);
          (*(void (__fastcall **)(Gfx *))(*(_QWORD *)v4 + 8LL))(v4);
          ARC::ExceptionScope::RethrowCachedException((ARC::ExceptionScope *)v8);
          ARC::ExceptionScope::~ExceptionScope((ARC::ExceptionScope *)v8);
        }
        catch ( const ARC::Exception *v7 )
        {
          ARC::ExceptionScope::Rethrow((ARC::ExceptionScope *)v8, v7);
          v2 = this;
          continue;
        }
        break;
      }
    }
    catch ( ... )
    {
      MsoShipAssertTagProc(512361817);
      v2 = this;
    }
  }
  Gfx::DiscardCachedResources(v2, v3);
}

```

## disassembly

```asm
0x1800a0c40  mov     [rsp+arg_18], rbx
0x1800a0c45  mov     [rsp+arg_0], rcx
0x1800a0c4a  push    rdi
0x1800a0c4b  sub     rsp, 0A0h
0x1800a0c52  mov     rdi, rcx
0x1800a0c55  mov     rax, [rcx]
0x1800a0c58  mov     rax, [rax+0C0h]
0x1800a0c5f  call    cs:__guard_dispatch_icall_fptr
0x1800a0c65  test    al, al
0x1800a0c67  jz      short loc_1800A0C81
0x1800a0c69  mov     rcx, rdi; this
0x1800a0c6c  mov     rbx, [rsp+0A8h+arg_18]
0x1800a0c74  add     rsp, 0A0h
0x1800a0c7b  pop     rdi
0x1800a0c7c  jmp     ?DiscardCachedResources@Gfx@@YAXAEBUIFactory@ARC@@@Z; Gfx::DiscardCachedResources(ARC::IFactory const &)
0x1800a0c81  mov     rdx, rdi
0x1800a0c84  lea     rcx, [rsp+0A8h+var_58]
0x1800a0c89  call    cs:__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z; ARC::ExceptionScope::ExceptionScope(ARC::IFactory const *)
0x1800a0c8f  nop
0x1800a0c90  mov     rax, [rdi]
0x1800a0c93  mov     [rsp+0A8h+var_80], 0
0x1800a0c9c  mov     [rsp+0A8h+var_88], 0
0x1800a0ca5  xor     r9d, r9d
0x1800a0ca8  or      r8d, 0FFFFFFFFh
0x1800a0cac  lea     rdx, [rsp+0A8h+arg_8]
0x1800a0cb4  mov     rcx, rdi
0x1800a0cb7  mov     rax, [rax+0B0h]
0x1800a0cbe  call    cs:__guard_dispatch_icall_fptr
0x1800a0cc4  mov     rbx, [rax]
0x1800a0cc7  mov     [rsp+0A8h+arg_10], rbx
0x1800a0ccf  mov     rax, [rbx]
0x1800a0cd2  mov     rcx, rbx
0x1800a0cd5  mov     rax, [rax]
0x1800a0cd8  call    cs:__guard_dispatch_icall_fptr
0x1800a0cde  mov     rcx, [rsp+0A8h+arg_8]
0x1800a0ce6  test    rcx, rcx
0x1800a0ce9  jz      short loc_1800A0CF8
0x1800a0ceb  mov     rax, [rcx]
0x1800a0cee  mov     rax, [rax+8]
0x1800a0cf2  call    cs:__guard_dispatch_icall_fptr
0x1800a0cf8  mov     rcx, rbx; this
0x1800a0cfb  call    ?DestroyResourceCaches@Gfx@@YAXAEAUIDevice@ARC@@@Z; Gfx::DestroyResourceCaches(ARC::IDevice &)
0x1800a0d00  mov     rcx, rbx; this
0x1800a0d03  call    ?DestroyModel3DCacheOnDeviceRelease@Gfx@@YAXAEAUIDeviceContext@ARC@@@Z; Gfx::DestroyModel3DCacheOnDeviceRelease(ARC::IDeviceContext &)
0x1800a0d08  mov     rax, [rbx]
0x1800a0d0b  mov     rcx, rbx
0x1800a0d0e  mov     rax, [rax+8]
0x1800a0d12  call    cs:__guard_dispatch_icall_fptr
0x1800a0d18  lea     rcx, [rsp+0A8h+var_58]
0x1800a0d1d  call    cs:__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ; ARC::ExceptionScope::RethrowCachedException(void)
0x1800a0d23  lea     rcx, [rsp+0A8h+var_58]
0x1800a0d28  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x1800a0d2e  jmp     loc_1800A0C69
0x1800a0d33  mov     rdi, [rsp+0A8h+arg_0]
0x1800a0d3b  jmp     loc_1800A0C90
0x1800a0d40  mov     rdi, [rsp+0A8h+arg_0]
0x1800a0d48  jmp     loc_1800A0C69
```
