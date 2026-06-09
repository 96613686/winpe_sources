# ATL::CComObject<CEnhancedStorageEnumerator>::CreateInstance(ATL::CComObject<CEnhancedStorageEnumerator> * *)

- ea: `0x1800019d0`
- end: `0x180001b1a`
- name: `?CreateInstance@?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@SAJPEAPEAV12@@Z`
- size: `330`
- prototype: `__int64 __fastcall(CEnhancedStorageEnumerator **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001890`

## callees

- `0x1800019d0`
- `0x180001b20`
- `0x18000684c`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageEnumerator>::CreateInstance(CEnhancedStorageEnumerator **a1)
{
  CEnhancedStorageEnumerator **v1; // rdi
  CEnhancedStorageEnumerator *v2; // rax
  __int64 v3; // r9
  CEnhancedStorageEnumerator *v4; // rbx
  int v5; // eax
  int v6; // eax
  int v7; // ecx
  unsigned int v8; // r14d

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v8 = -2147024882;
    v2 = (CEnhancedStorageEnumerator *)operator new(0x28u);
  }
  catch ( ... )
  {
    v1 = a1;
    v8 = -2147024882;
    v4 = 0;
    goto LABEL_8;
  }
  v4 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v3);
    *(_QWORD *)v4 = &ATL::CComObject<CEnhancedStorageEnumerator>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v4 = 0;
  }
LABEL_8:
  if ( v4 )
  {
    v5 = *((_DWORD *)v4 + 2);
    if ( v5 != 0x7FFFFFFF )
      *((_DWORD *)v4 + 2) = v5 + 1;
    v6 = CEnhancedStorageEnumerator::FinalConstruct(v4);
    v7 = *((_DWORD *)v4 + 2);
    v8 = 0;
    if ( v6 < 0 )
      v8 = v6;
    if ( v7 != 0x7FFFFFFF )
      *((_DWORD *)v4 + 2) = v7 - 1;
    if ( v8 )
    {
      (*(void (__fastcall **)(CEnhancedStorageEnumerator *, __int64))(*(_QWORD *)v4 + 56LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      v8 = 0;
    }
  }
  *v1 = v4;
  return v8;
}

```

## disassembly

```asm
0x1800019d0  mov     [rsp+arg_18], rbx
0x1800019d5  mov     [rsp+arg_0], rcx
0x1800019da  push    rsi
0x1800019db  push    rdi
0x1800019dc  push    r14
0x1800019de  sub     rsp, 20h
0x1800019e2  mov     rdi, rcx
0x1800019e5  test    rcx, rcx
0x1800019e8  jz      loc_180001ABE
0x1800019ee  xor     esi, esi
0x1800019f0  mov     [rcx], rsi
0x1800019f3  mov     r14d, 8007000Eh
0x1800019f9  mov     [rsp+38h+arg_8], r14d
0x1800019fe  mov     [rsp+38h+arg_10], rsi
0x180001a03  mov     ecx, 28h ; '('; Size
0x180001a08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a0d  mov     rbx, rax
0x180001a10  test    rax, rax
0x180001a13  jz      loc_180001AB9
0x180001a19  mov     [rax+8], esi
0x180001a1c  mov     [rax+10h], rsi
0x180001a20  mov     [rax+18h], rsi
0x180001a24  mov     [rax+20h], rsi
0x180001a28  lea     rax, WPP_GLOBAL_Control
0x180001a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a36  cmp     rcx, rax
0x180001a39  jz      short loc_180001A45
0x180001a3b  test    byte ptr [rcx+1Ch], 20h
0x180001a3f  jnz     loc_180001AD1
0x180001a45  lea     rax, ??_7?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageEnumerator>::`vftable'
0x180001a4c  mov     [rbx], rax
0x180001a4f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001a56  mov     rax, [rcx]
0x180001a59  mov     rax, [rax+8]
0x180001a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a62  mov     [rsp+38h+arg_10], rbx
0x180001a67  test    rbx, rbx
0x180001a6a  jz      short loc_180001AA5
0x180001a6c  mov     eax, [rbx+8]
0x180001a6f  cmp     eax, 7FFFFFFFh
0x180001a74  jz      short loc_180001A7B
0x180001a76  inc     eax
0x180001a78  mov     [rbx+8], eax
0x180001a7b  mov     rcx, rbx; this
0x180001a7e  call    ?FinalConstruct@CEnhancedStorageEnumerator@@QEAAJXZ; CEnhancedStorageEnumerator::FinalConstruct(void)
0x180001a83  mov     ecx, [rbx+8]
0x180001a86  mov     r14d, esi
0x180001a89  test    eax, eax
0x180001a8b  cmovs   r14d, eax
0x180001a8f  cmp     ecx, 7FFFFFFFh
0x180001a95  jz      short loc_180001A9D
0x180001a97  lea     eax, [rcx-1]
0x180001a9a  mov     [rbx+8], eax
0x180001a9d  test    r14d, r14d
0x180001aa0  jnz     short loc_180001B01
0x180001aa2  mov     r14d, esi
0x180001aa5  mov     [rdi], rbx
0x180001aa8  mov     eax, r14d
0x180001aab  mov     rbx, [rsp+38h+arg_18]
0x180001ab0  add     rsp, 20h
0x180001ab4  pop     r14
0x180001ab6  pop     rdi
0x180001ab7  pop     rsi
0x180001ab8  retn
0x180001ab9  mov     rbx, rsi
0x180001abc  jmp     short loc_180001A62
0x180001abe  mov     eax, 80004003h
0x180001ac3  mov     rbx, [rsp+38h+arg_18]
0x180001ac8  add     rsp, 20h
0x180001acc  pop     r14
0x180001ace  pop     rdi
0x180001acf  pop     rsi
0x180001ad0  retn
0x180001ad1  mov     edx, 0Ah
0x180001ad6  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180001add  mov     rcx, [rcx+10h]
0x180001ae1  call    WPP_SF_
0x180001ae6  jmp     loc_180001A45
0x180001aeb  xor     esi, esi
0x180001aed  mov     rdi, [rsp+38h+arg_0]
0x180001af2  mov     r14d, [rsp+38h+arg_8]
0x180001af7  mov     rbx, [rsp+38h+arg_10]
0x180001afc  jmp     loc_180001A67
0x180001b01  mov     rax, [rbx]
0x180001b04  mov     edx, 1
0x180001b09  mov     rcx, rbx
0x180001b0c  mov     rax, [rax+38h]
0x180001b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b15  mov     rbx, rsi
0x180001b18  jmp     short loc_180001AA5
```
