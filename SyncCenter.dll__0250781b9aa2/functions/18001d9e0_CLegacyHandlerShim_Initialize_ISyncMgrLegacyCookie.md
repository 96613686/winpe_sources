# CLegacyHandlerShim::Initialize(ISyncMgrLegacyCookie *)

- ea: `0x18001d9e0`
- end: `0x18001db16`
- name: `?Initialize@CLegacyHandlerShim@@QEAAJPEAUISyncMgrLegacyCookie@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(CLegacyHandlerShim *__hidden this, struct ISyncMgrLegacyCookie *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001dbc0`

## callees

- `0x180009940`
- `0x18000a5e4`
- `0x18001d9e0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001da89`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001daa0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dab7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dace`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001da89`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001daa0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dab7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dace`

## pseudocode

```c
__int64 __fastcall CLegacyHandlerShim::Initialize(CLegacyHandlerShim *this, struct ISyncMgrLegacyCookie *a2)
{
  void *v2; // rdi
  int v5; // ebx
  LPVOID v6; // rax
  HANDLE EventW; // rax
  bool v8; // zf
  unsigned __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  LODWORD(v10) = 0;
  if ( !a2
    || (v5 = (*(__int64 (__fastcall **)(struct ISyncMgrLegacyCookie *, unsigned __int64 *))(*(_QWORD *)a2 + 24LL))(
               a2,
               &v10),
        v5 >= 0)
    && ((v6 = operator new((unsigned int)v10), (v2 = v6) == 0)
     || (v5 = (*(__int64 (__fastcall **)(struct ISyncMgrLegacyCookie *, LPVOID, _QWORD))(*(_QWORD *)a2 + 32LL))(
                a2,
                v6,
                (unsigned int)v10),
         v5 >= 0)) )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 30) + 24LL))(
           *((_QWORD *)this + 30),
           0,
           5);
    if ( v5 >= 0 )
    {
      *((_QWORD *)this + 32) = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 31) = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 36) = CreateEventW(0, 1, 0, 0);
      EventW = CreateEventW(0, 1, 0, 0);
      v8 = *((_QWORD *)this + 32) == 0;
      *((_QWORD *)this + 37) = EventW;
      if ( v8 || !*((_QWORD *)this + 31) || !*((_QWORD *)this + 36) || !EventW )
        v5 = -2147024882;
    }
  }
  CZeroInitNew::operator delete(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d9e0  push    rbx
0x18001d9e2  push    rbp
0x18001d9e3  push    rsi
0x18001d9e4  push    rdi
0x18001d9e5  sub     rsp, 38h
0x18001d9e9  xor     r9d, r9d
0x18001d9ec  xor     edi, edi
0x18001d9ee  mov     dword ptr [rsp+58h+arg_8], r9d
0x18001d9f3  mov     rsi, rdx
0x18001d9f6  mov     rbp, rcx
0x18001d9f9  test    rdx, rdx
0x18001d9fc  jz      short loc_18001DA53
0x18001d9fe  mov     rax, [rdx]
0x18001da01  mov     rcx, rsi
0x18001da04  lea     rdx, [rsp+58h+arg_8]
0x18001da09  mov     rax, [rax+18h]
0x18001da0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da12  mov     ebx, eax
0x18001da14  test    eax, eax
0x18001da16  js      loc_18001DB03
0x18001da1c  mov     ecx, dword ptr [rsp+58h+arg_8]; unsigned __int64
0x18001da20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001da25  mov     rdi, rax
0x18001da28  test    rax, rax
0x18001da2b  jz      short loc_18001DA4E
0x18001da2d  mov     rcx, [rsi]
0x18001da30  mov     rdx, rdi
0x18001da33  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18001da38  mov     rax, [rcx+20h]
0x18001da3c  mov     rcx, rsi
0x18001da3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da44  mov     ebx, eax
0x18001da46  test    eax, eax
0x18001da48  js      loc_18001DB03
0x18001da4e  mov     r9d, dword ptr [rsp+58h+arg_8]
0x18001da53  mov     rcx, [rbp+0F0h]
0x18001da5a  xor     edx, edx
0x18001da5c  mov     [rsp+58h+var_38], rdi
0x18001da61  mov     rax, [rcx]
0x18001da64  lea     r8d, [rdx+5]
0x18001da68  mov     rax, [rax+18h]
0x18001da6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da71  mov     ebx, eax
0x18001da73  test    eax, eax
0x18001da75  js      loc_18001DB03
0x18001da7b  xor     r9d, r9d; lpName
0x18001da7e  xor     r8d, r8d; bInitialState
0x18001da81  xor     ecx, ecx; lpEventAttributes
0x18001da83  lea     esi, [r9+1]
0x18001da87  mov     edx, esi; bManualReset
0x18001da89  call    cs:__imp_CreateEventW
0x18001da8f  xor     r9d, r9d; lpName
0x18001da92  xor     r8d, r8d; bInitialState
0x18001da95  mov     edx, esi; bManualReset
0x18001da97  mov     [rbp+100h], rax
0x18001da9e  xor     ecx, ecx; lpEventAttributes
0x18001daa0  call    cs:__imp_CreateEventW
0x18001daa6  xor     r9d, r9d; lpName
0x18001daa9  xor     r8d, r8d; bInitialState
0x18001daac  mov     edx, esi; bManualReset
0x18001daae  mov     [rbp+0F8h], rax
0x18001dab5  xor     ecx, ecx; lpEventAttributes
0x18001dab7  call    cs:__imp_CreateEventW
0x18001dabd  xor     r9d, r9d; lpName
0x18001dac0  xor     r8d, r8d; bInitialState
0x18001dac3  mov     edx, esi; bManualReset
0x18001dac5  mov     [rbp+120h], rax
0x18001dacc  xor     ecx, ecx; lpEventAttributes
0x18001dace  call    cs:__imp_CreateEventW
0x18001dad4  cmp     qword ptr [rbp+100h], 0
0x18001dadc  mov     [rbp+128h], rax
0x18001dae3  jz      short loc_18001DAFE
0x18001dae5  cmp     qword ptr [rbp+0F8h], 0
0x18001daed  jz      short loc_18001DAFE
0x18001daef  cmp     qword ptr [rbp+120h], 0
0x18001daf7  jz      short loc_18001DAFE
0x18001daf9  test    rax, rax
0x18001dafc  jnz     short loc_18001DB03
0x18001dafe  mov     ebx, 8007000Eh
0x18001db03  mov     rcx, rdi; lpMem
0x18001db06  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18001db0b  mov     eax, ebx
0x18001db0d  add     rsp, 38h
0x18001db11  pop     rdi
0x18001db12  pop     rsi
0x18001db13  pop     rbp
0x18001db14  pop     rbx
0x18001db15  retn
```
