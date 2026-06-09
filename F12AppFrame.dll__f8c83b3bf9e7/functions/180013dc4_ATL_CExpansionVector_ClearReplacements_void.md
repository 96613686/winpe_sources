# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180013dc4`
- end: `0x180013e6c`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012474`
- `0x180013e80`

## callees

- `0x180001900`
- `0x180006e00`
- `0x180013dc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e2f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e2f`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, int a2, unsigned int a3)
{
  int v3; // eax
  int i; // edi
  int v6; // edx
  unsigned int v7; // r8d
  void *v8; // rcx
  __int64 result; // rax

  v3 = *((_DWORD *)this + 4);
  if ( v3 > 0 )
  {
    for ( i = 0; i < v3; ++i )
    {
      if ( i < 0 || i >= v3 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, a2, a3);
        __debugbreak();
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v6, v7);
        JUMPOUT(0x180013E6BLL);
      }
      operator delete(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v3 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    free(v8);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180013dc4  mov     [rsp+arg_0], rbx
0x180013dc9  mov     [rsp+arg_8], rsi
0x180013dce  push    rdi
0x180013dcf  sub     rsp, 20h
0x180013dd3  mov     eax, [rcx+10h]
0x180013dd6  mov     rbx, rcx
0x180013dd9  test    eax, eax
0x180013ddb  jle     short loc_180013E11
0x180013ddd  xor     edi, edi
0x180013ddf  test    edi, edi
0x180013de1  js      short loc_180013E56
0x180013de3  cmp     edi, eax
0x180013de5  jge     short loc_180013E56
0x180013de7  mov     rcx, [rbx]
0x180013dea  movsxd  rsi, edi
0x180013ded  mov     rcx, [rcx+rsi*8]; Block
0x180013df1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013df6  cmp     edi, [rbx+10h]
0x180013df9  jge     short loc_180013E61
0x180013dfb  mov     rcx, [rbx+8]
0x180013dff  mov     rcx, [rcx+rsi*8]; Block
0x180013e03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013e08  mov     eax, [rbx+10h]
0x180013e0b  inc     edi
0x180013e0d  cmp     edi, eax
0x180013e0f  jl      short loc_180013DDF
0x180013e11  mov     rcx, [rbx]; Block
0x180013e14  test    rcx, rcx
0x180013e17  jz      short loc_180013E26
0x180013e19  call    cs:__imp_free
0x180013e1f  mov     qword ptr [rbx], 0
0x180013e26  mov     rcx, [rbx+8]; Block
0x180013e2a  test    rcx, rcx
0x180013e2d  jz      short loc_180013E3D
0x180013e2f  call    cs:__imp_free
0x180013e35  mov     qword ptr [rbx+8], 0
0x180013e3d  mov     rsi, [rsp+28h+arg_8]
0x180013e42  xor     eax, eax
0x180013e44  mov     dword ptr [rbx+10h], 0
0x180013e4b  mov     rbx, [rsp+28h+arg_0]
0x180013e50  add     rsp, 20h
0x180013e54  pop     rdi
0x180013e55  retn
0x180013e56  mov     ecx, 0C000008Ch; this
0x180013e5b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180013e60  int     3; Trap to Debugger
0x180013e61  mov     ecx, 0C000008Ch; this
0x180013e66  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
