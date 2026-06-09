# ATL::CComObject<CGenericEnum>::CreateInstance(ATL::CComObject<CGenericEnum> * *)

- ea: `0x180005ea0`
- end: `0x180005f9b`
- name: `?CreateInstance@?$CComObject@VCGenericEnum@@@ATL@@SAJPEAPEAV12@@Z`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004490`
- `0x180005000`
- `0x180016718`

## callees

- `0x180005ea0`
- `0x180006230`
- `0x18000f088`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGenericEnum>::CreateInstance(_QWORD *a1)
{
  int v2; // edi
  char *v3; // rax
  _BYTE *v4; // rbx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v2 = -2147024882;
  v3 = (char *)operator new(0x70u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 6) = 0;
    v3[56] = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *((_DWORD *)v3 + 22) = 0;
    *(GUID *)(v3 + 92) = GUID_00000000_0000_0000_c000_000000000046;
    *(_QWORD *)v3 = &ATL::CComObject<CGenericEnum>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v4 = 0;
  }
  if ( v4 )
  {
    v2 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v4 + 16));
    if ( v2 < 0 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v4 + 56LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      v4[56] = 1;
      v2 = 0;
    }
  }
  *a1 = v4;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180005ea0  mov     [rsp+arg_0], rcx
0x180005ea5  push    rbx
0x180005ea6  push    rsi
0x180005ea7  push    rdi
0x180005ea8  push    r14
0x180005eaa  push    r15
0x180005eac  sub     rsp, 20h
0x180005eb0  mov     rsi, rcx
0x180005eb3  test    rcx, rcx
0x180005eb6  jz      loc_180005F63
0x180005ebc  xor     r14d, r14d
0x180005ebf  mov     [rcx], r14
0x180005ec2  mov     edi, 8007000Eh
0x180005ec7  mov     [rsp+48h+arg_8], edi
0x180005ecb  mov     [rsp+48h+arg_10], r14
0x180005ed0  mov     ecx, 70h ; 'p'; Size
0x180005ed5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005eda  mov     rbx, rax
0x180005edd  test    rax, rax
0x180005ee0  jz      loc_180005F6A
0x180005ee6  mov     [rax+8], r14d
0x180005eea  xorps   xmm0, xmm0
0x180005eed  xor     eax, eax
0x180005eef  movups  xmmword ptr [rbx+10h], xmm0
0x180005ef3  movups  xmmword ptr [rbx+20h], xmm0
0x180005ef7  mov     [rbx+30h], rax
0x180005efb  mov     [rbx+38h], al
0x180005efe  mov     [rbx+40h], r14
0x180005f02  mov     [rbx+48h], r14
0x180005f06  mov     [rbx+58h], r14d
0x180005f0a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x180005f11  movups  xmmword ptr [rbx+5Ch], xmm0
0x180005f15  lea     rax, ??_7?$CComObject@VCGenericEnum@@@ATL@@6B@; const ATL::CComObject<CGenericEnum>::`vftable'
0x180005f1c  mov     [rbx], rax
0x180005f1f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005f26  mov     rax, [rcx]
0x180005f29  mov     rax, [rax+8]
0x180005f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f32  mov     [rsp+48h+arg_10], rbx
0x180005f37  test    rbx, rbx
0x180005f3a  jz      short loc_180005F52
0x180005f3c  lea     rcx, [rbx+10h]; this
0x180005f40  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005f45  mov     edi, eax
0x180005f47  test    eax, eax
0x180005f49  js      short loc_180005F82
0x180005f4b  mov     byte ptr [rbx+38h], 1
0x180005f4f  mov     edi, r14d
0x180005f52  mov     [rsi], rbx
0x180005f55  mov     eax, edi
0x180005f57  add     rsp, 20h
0x180005f5b  pop     r15
0x180005f5d  pop     r14
0x180005f5f  pop     rdi
0x180005f60  pop     rsi
0x180005f61  pop     rbx
0x180005f62  retn
0x180005f63  mov     eax, 80004003h
0x180005f68  jmp     short loc_180005F57
0x180005f6a  mov     rbx, r14
0x180005f6d  jmp     short loc_180005F32
0x180005f6f  xor     r14d, r14d
0x180005f72  mov     rsi, [rsp+48h+arg_0]
0x180005f77  mov     edi, [rsp+48h+arg_8]
0x180005f7b  mov     rbx, [rsp+48h+arg_10]
0x180005f80  jmp     short loc_180005F37
0x180005f82  mov     rcx, [rbx]
0x180005f85  mov     rax, [rcx+38h]
0x180005f89  mov     edx, 1
0x180005f8e  mov     rcx, rbx
0x180005f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f96  mov     rbx, r14
0x180005f99  jmp     short loc_180005F52
```
