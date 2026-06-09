# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140010620`
- end: `0x140010682`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140010620`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140010620  sub     rsp, 28h
0x140010624  mov     r11, rcx
0x140010627  mov     rax, r8
0x14001062a  xor     ecx, ecx
0x14001062c  mov     r10, rdx
0x14001062f  mov     r8d, 80004003h
0x140010635  test    r9, r9
0x140010638  jz      short loc_14001067A
0x14001063a  mov     [r9], rcx
0x14001063d  test    rdx, rdx
0x140010640  jz      short loc_140010665
0x140010642  cmp     [rax], ecx
0x140010644  jnz     short loc_14001065D
0x140010646  cmp     [rax+4], ecx
0x140010649  jnz     short loc_14001065D
0x14001064b  cmp     dword ptr [rax+8], 0C0h
0x140010652  jnz     short loc_14001065D
0x140010654  cmp     dword ptr [rax+0Ch], 46000000h
0x14001065b  jz      short loc_140010665
0x14001065d  mov     r8d, 80040110h
0x140010663  jmp     short loc_14001067A
0x140010665  mov     rdx, rax
0x140010668  mov     r8, r9
0x14001066b  mov     rax, [r11+40h]
0x14001066f  mov     rcx, r10
0x140010672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010677  mov     r8d, eax
0x14001067a  mov     eax, r8d
0x14001067d  add     rsp, 28h
0x140010681  retn
```
