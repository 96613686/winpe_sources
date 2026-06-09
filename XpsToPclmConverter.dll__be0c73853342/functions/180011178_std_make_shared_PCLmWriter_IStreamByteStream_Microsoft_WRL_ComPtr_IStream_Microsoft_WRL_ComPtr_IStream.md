# std::make_shared<PCLmWriter::IStreamByteStream,Microsoft::WRL::ComPtr<IStream> &>(Microsoft::WRL::ComPtr<IStream> &)

- ea: `0x180011178`
- end: `0x18001122f`
- name: `??$make_shared@VIStreamByteStream@PCLmWriter@@AEAV?$ComPtr@UIStream@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@VIStreamByteStream@PCLmWriter@@@0@AEAV?$ComPtr@UIStream@@@WRL@Microsoft@@@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012630`

## callees

- `0x180001f6c`
- `0x1800101cc`
- `0x180010204`
- `0x180010a9c`
- `0x180011178`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<PCLmWriter::IStreamByteStream,Microsoft::WRL::ComPtr<IStream> &>(
        _QWORD *a1,
        __int64 a2)
{
  char *v4; // rdi
  char *v5; // rsi
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx

  v4 = (char *)operator new(0x60u);
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  v5 = v4 + 16;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count_obj2<PCLmWriter::IStreamByteStream>::`vftable';
  std::_Construct_in_place<PCLmWriter::IStreamByteStream,Microsoft::WRL::ComPtr<IStream> &>(v4 + 16, a2);
  *a1 = v4 + 16;
  a1[1] = v4;
  if ( v4 != (char *)-16LL )
  {
    v6 = *((_QWORD *)v4 + 5);
    if ( !v6 || !*(_DWORD *)(v6 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
      v7 = (volatile signed __int32 *)a1[1];
      if ( v7 )
      {
        v8 = a1[1];
        _InterlockedIncrement(v7 + 3);
      }
      else
      {
        v8 = 0;
        v5 = 0;
      }
      *((_QWORD *)v4 + 4) = v5;
      v9 = (std::_Ref_count_base *)*((_QWORD *)v4 + 5);
      *((_QWORD *)v4 + 5) = v8;
      if ( v9 )
        std::_Ref_count_base::_Decwref(v9);
      if ( v7 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v7);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180011178  push    rbx
0x18001117a  push    rsi
0x18001117b  push    rdi
0x18001117c  push    r14
0x18001117e  sub     rsp, 38h
0x180011182  mov     r14, rcx
0x180011185  mov     rbx, rdx
0x180011188  mov     ecx, 60h ; '`'; Size
0x18001118d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011192  mov     [rsp+58h+arg_0], rax
0x180011197  mov     rdi, rax
0x18001119a  xorps   xmm0, xmm0
0x18001119d  mov     rdx, rbx
0x1800111a0  movups  xmmword ptr [rax], xmm0
0x1800111a3  mov     dword ptr [rax+8], 1
0x1800111aa  lea     rsi, [rdi+10h]
0x1800111ae  mov     dword ptr [rax+0Ch], 1
0x1800111b5  mov     rcx, rsi
0x1800111b8  lea     rax, ??_7?$_Ref_count_obj2@VIStreamByteStream@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::IStreamByteStream>::`vftable'
0x1800111bf  mov     [rdi], rax
0x1800111c2  call    ??$_Construct_in_place@VIStreamByteStream@PCLmWriter@@AEAV?$ComPtr@UIStream@@@WRL@Microsoft@@@std@@YAXAEAVIStreamByteStream@PCLmWriter@@AEAV?$ComPtr@UIStream@@@WRL@Microsoft@@@Z; std::_Construct_in_place<PCLmWriter::IStreamByteStream,Microsoft::WRL::ComPtr<IStream> &>(PCLmWriter::IStreamByteStream &,Microsoft::WRL::ComPtr<IStream> &)
0x1800111c7  mov     [r14], rsi
0x1800111ca  mov     [r14+8], rdi
0x1800111ce  test    rsi, rsi
0x1800111d1  jz      short loc_180011222
0x1800111d3  lea     rax, [rsi+10h]
0x1800111d7  mov     rcx, [rax+8]
0x1800111db  test    rcx, rcx
0x1800111de  jz      short loc_1800111E6
0x1800111e0  cmp     dword ptr [rcx+8], 0
0x1800111e4  jnz     short loc_180011222
0x1800111e6  lock inc dword ptr [rdi+8]
0x1800111ea  mov     rbx, [r14+8]
0x1800111ee  test    rbx, rbx
0x1800111f1  jz      short loc_1800111FC
0x1800111f3  mov     rdx, rbx
0x1800111f6  lock inc dword ptr [rbx+0Ch]
0x1800111fa  jmp     short loc_180011200
0x1800111fc  xor     edx, edx
0x1800111fe  xor     esi, esi
0x180011200  mov     [rax], rsi
0x180011203  mov     rcx, [rax+8]; this
0x180011207  mov     [rax+8], rdx
0x18001120b  test    rcx, rcx
0x18001120e  jz      short loc_180011215
0x180011210  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011215  test    rbx, rbx
0x180011218  jz      short loc_180011222
0x18001121a  mov     rcx, rbx; this
0x18001121d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011222  mov     rax, r14
0x180011225  add     rsp, 38h
0x180011229  pop     r14
0x18001122b  pop     rdi
0x18001122c  pop     rsi
0x18001122d  pop     rbx
0x18001122e  retn
```
