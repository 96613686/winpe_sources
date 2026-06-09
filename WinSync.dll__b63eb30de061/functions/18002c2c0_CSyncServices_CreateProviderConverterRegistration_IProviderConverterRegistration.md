# CSyncServices::CreateProviderConverterRegistration(IProviderConverterRegistration * *)

- ea: `0x18002c2c0`
- end: `0x18002c3b9`
- name: `?CreateProviderConverterRegistration@CSyncServices@@UEAAJPEAPEAUIProviderConverterRegistration@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct IProviderConverterRegistration **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002c2c0`
- `0x180081690`
- `0x180094010`

## string_xrefs

- `0x18002c2f5`: `CSyncServices::CreateProviderConverterRegistration`
- `0x18002c38b`: `CSyncServices::CreateProviderConverterRegistration`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateProviderConverterRegistration(
        CSyncServices *this,
        struct IProviderConverterRegistration **a2)
{
  PVOID *v3; // rcx
  unsigned int v4; // ebx
  ProviderConverterRegistration *v5; // rax
  ProviderConverterRegistration *v6; // rax
  ProviderConverterRegistration *v7; // rdi

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateProviderConverterRegistration");
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v5 = (ProviderConverterRegistration *)SeAlloc(0x20u);
    if ( v5 && (v6 = ProviderConverterRegistration::ProviderConverterRegistration(v5), (v7 = v6) != 0) )
    {
      v4 = (**(__int64 (__fastcall ***)(ProviderConverterRegistration *, GUID *, struct IProviderConverterRegistration **))v6)(
             v6,
             &GUID_9a9ea1eb_9033_40eb_a891_9693d41d7401,
             a2);
      (*(void (__fastcall **)(ProviderConverterRegistration *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    else
    {
      v4 = -2147024882;
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v4 = -2147467261;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v3[2],
      59,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateProviderConverterRegistration",
      v4);
  return v4;
}

```

## disassembly

```asm
0x18002c2c0  mov     [rsp+arg_0], rbx
0x18002c2c5  mov     [rsp+arg_8], rsi
0x18002c2ca  push    rdi
0x18002c2cb  sub     rsp, 30h
0x18002c2cf  mov     rbx, rdx
0x18002c2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2d9  lea     rsi, WPP_GLOBAL_Control
0x18002c2e0  cmp     rcx, rsi
0x18002c2e3  jz      short loc_18002C314
0x18002c2e5  test    byte ptr [rcx+1Ch], 2
0x18002c2e9  jz      short loc_18002C314
0x18002c2eb  cmp     byte ptr [rcx+19h], 5
0x18002c2ef  jb      short loc_18002C314
0x18002c2f1  mov     rcx, [rcx+10h]
0x18002c2f5  lea     r9, aCsyncservicesC_9; "CSyncServices::CreateProviderConverterR"...
0x18002c2fc  mov     edx, 3Ah ; ':'
0x18002c301  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c308  call    WPP_SF_s
0x18002c30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c314  test    rbx, rbx
0x18002c317  jnz     short loc_18002C320
0x18002c319  mov     ebx, 80004003h
0x18002c31e  jmp     short loc_18002C376
0x18002c320  mov     ecx, 20h ; ' '; unsigned __int64
0x18002c325  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c32a  test    rax, rax
0x18002c32d  jz      short loc_18002C36A
0x18002c32f  mov     rcx, rax; this
0x18002c332  call    ??0ProviderConverterRegistration@@QEAA@XZ; ProviderConverterRegistration::ProviderConverterRegistration(void)
0x18002c337  mov     rdi, rax
0x18002c33a  test    rax, rax
0x18002c33d  jz      short loc_18002C36A
0x18002c33f  mov     rax, [rax]
0x18002c342  lea     rdx, _GUID_9a9ea1eb_9033_40eb_a891_9693d41d7401
0x18002c349  mov     r8, rbx
0x18002c34c  mov     rcx, rdi
0x18002c34f  mov     rax, [rax]
0x18002c352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c357  mov     rcx, [rdi]
0x18002c35a  mov     ebx, eax
0x18002c35c  mov     rax, [rcx+10h]
0x18002c360  mov     rcx, rdi
0x18002c363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c368  jmp     short loc_18002C36F
0x18002c36a  mov     ebx, 8007000Eh
0x18002c36f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c376  cmp     rcx, rsi
0x18002c379  jz      short loc_18002C3A7
0x18002c37b  test    byte ptr [rcx+1Ch], 2
0x18002c37f  jz      short loc_18002C3A7
0x18002c381  cmp     byte ptr [rcx+19h], 5
0x18002c385  jb      short loc_18002C3A7
0x18002c387  mov     rcx, [rcx+10h]
0x18002c38b  lea     r9, aCsyncservicesC_9; "CSyncServices::CreateProviderConverterR"...
0x18002c392  mov     edx, 3Bh ; ';'
0x18002c397  mov     [rsp+38h+var_18], ebx
0x18002c39b  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c3a2  call    WPP_SF_sD
0x18002c3a7  mov     rsi, [rsp+38h+arg_8]
0x18002c3ac  mov     eax, ebx
0x18002c3ae  mov     rbx, [rsp+38h+arg_0]
0x18002c3b3  add     rsp, 30h
0x18002c3b7  pop     rdi
0x18002c3b8  retn
```
