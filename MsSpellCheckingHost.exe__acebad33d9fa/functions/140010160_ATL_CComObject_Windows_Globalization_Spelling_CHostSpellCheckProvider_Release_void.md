# ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release(void)

- ea: `0x140010160`
- end: `0x1400101e1`
- name: `?Release@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400101f0`
- `0x140010200`

## callees

- `0x140010160`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release(
        volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 6);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 6, i - 1, i);
        i = *((_DWORD *)a1 + 6) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140010160  mov     [rsp+arg_0], rbx
0x140010165  push    rdi
0x140010166  sub     rsp, 20h
0x14001016a  mov     r8d, [rcx+18h]
0x14001016e  mov     rbx, rcx
0x140010171  mov     ecx, 7FFFFFFFh
0x140010176  jmp     short loc_14001018A
0x140010178  lea     edx, [r8-1]
0x14001017c  mov     eax, r8d
0x14001017f  lock cmpxchg [rbx+18h], edx
0x140010184  jz      short loc_14001018F
0x140010186  mov     r8d, [rbx+18h]
0x14001018a  cmp     r8d, ecx
0x14001018d  jnz     short loc_140010178
0x14001018f  lea     edi, [r8-1]
0x140010193  test    edi, edi
0x140010195  jnz     short loc_1400101D4
0x140010197  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14001019e  mov     rax, [rcx]
0x1400101a1  mov     rax, [rax+8]
0x1400101a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101aa  test    rbx, rbx
0x1400101ad  jz      short loc_1400101C1
0x1400101af  mov     rax, [rbx]
0x1400101b2  lea     edx, [rdi+1]
0x1400101b5  mov     rcx, rbx
0x1400101b8  mov     rax, [rax+70h]
0x1400101bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101c1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400101c8  mov     rdx, [rcx]
0x1400101cb  mov     rax, [rdx+10h]
0x1400101cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101d4  mov     rbx, [rsp+28h+arg_0]
0x1400101d9  mov     eax, edi
0x1400101db  add     rsp, 20h
0x1400101df  pop     rdi
0x1400101e0  retn
```
