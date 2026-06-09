# ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(IUnknown *,IUnknown * *)

- ea: `0x180022c0c`
- end: `0x180022c6a`
- name: `?_SerializeDeserializeData@MtfTransportClientCoreUI@mtf@ipx@@IEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `94`
- prototype: `int(ipx::mtf::MtfTransportClientCoreUI *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180020110`
- `0x180022728`

## callees

- `0x180022c0c`
- `0x180023e18`
- `0x1800243f0`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(
        ipx::mtf::MtfTransportClientCoreUI *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  struct IUnknown *v5; // rdx

  if ( *((_BYTE *)this + 272) )
    return ipx::mtf::TransportLib_SerializeToStream((ipx::mtf *)a2, (struct IUnknown *)a3, a3);
  if ( *((_BYTE *)this + 273) )
  {
    v5 = (struct IUnknown *)a3;
    LOBYTE(a3) = *((_DWORD *)this + 66) != 32;
    return ipx::mtf::TransportLib_DeserializeFromStream(
             (__int64 (__fastcall ***)(ipx::mtf *, GUID *, LPSTREAM *))a2,
             v5,
             a3);
  }
  else
  {
    *a3 = a2;
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    return 0;
  }
}

```

## disassembly

```asm
0x180022c0c  sub     rsp, 28h
0x180022c10  cmp     byte ptr [rcx+110h], 0
0x180022c17  mov     rax, r8
0x180022c1a  mov     r9, rdx; bool
0x180022c1d  jz      short loc_180022C2E
0x180022c1f  mov     rdx, rax; struct IUnknown *
0x180022c22  mov     rcx, r9; this
0x180022c25  add     rsp, 28h
0x180022c29  jmp     ?TransportLib_SerializeToStream@mtf@ipx@@YAJPEAUIUnknown@@PEAPEAU3@@Z; ipx::mtf::TransportLib_SerializeToStream(IUnknown *,IUnknown * *)
0x180022c2e  cmp     byte ptr [rcx+111h], 0
0x180022c35  jz      short loc_180022C51
0x180022c37  cmp     dword ptr [rcx+108h], 20h ; ' '
0x180022c3e  mov     rdx, rax; struct IUnknown *
0x180022c41  mov     rcx, r9; this
0x180022c44  setnz   r8b; struct IUnknown **
0x180022c48  add     rsp, 28h
0x180022c4c  jmp     ?TransportLib_DeserializeFromStream@mtf@ipx@@YAJPEAUIUnknown@@PEAPEAU3@_N@Z; ipx::mtf::TransportLib_DeserializeFromStream(IUnknown *,IUnknown * *,bool)
0x180022c51  mov     [r8], r9
0x180022c54  mov     rcx, r9
0x180022c57  mov     rax, [rdx]
0x180022c5a  mov     rax, [rax+8]
0x180022c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c63  xor     eax, eax
0x180022c65  add     rsp, 28h
0x180022c69  retn
```
