# CoSurrogate::LoadDllServer(_GUID const &)

- ea: `0x140002190`
- end: `0x140002206`
- name: `?LoadDllServer@CoSurrogate@@UEAAJAEBU_GUID@@@Z`
- size: `118`
- prototype: `HRESULT __fastcall(CoSurrogate *this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001360`
- `0x140002190`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400021f5`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400021f5`

## pseudocode

```c
HRESULT __fastcall CoSurrogate::LoadDllServer(CoSurrogate *this, const struct _GUID *a2)
{
  IUnknown *v4; // rdx

  v4 = (IUnknown *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    LODWORD(v4[3].lpVtbl) = 1;
    v4->lpVtbl = (struct IUnknownVtbl *)&SurrClassFactory::`vftable';
    v4[1].lpVtbl = 0;
    v4[2].lpVtbl = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 1) = v4;
  return CoRegisterClassObject(a2, v4, 4u, 0, (LPDWORD)this + 4);
}

```

## disassembly

```asm
0x140002190  mov     [rsp+arg_0], rbx
0x140002195  push    rdi
0x140002196  sub     rsp, 30h
0x14000219a  mov     rdi, rdx
0x14000219d  mov     rbx, rcx
0x1400021a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400021a7  mov     ecx, 20h ; ' '; unsigned __int64
0x1400021ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400021b1  mov     rdx, rax
0x1400021b4  test    rax, rax
0x1400021b7  jz      short loc_1400021DC
0x1400021b9  lea     rax, ??_7SurrClassFactory@@6B@; const SurrClassFactory::`vftable'
0x1400021c0  mov     dword ptr [rdx+18h], 1
0x1400021c7  mov     [rdx], rax
0x1400021ca  mov     qword ptr [rdx+8], 0
0x1400021d2  mov     qword ptr [rdx+10h], 0
0x1400021da  jmp     short loc_1400021DE
0x1400021dc  xor     edx, edx; pUnk
0x1400021de  xor     r9d, r9d; flags
0x1400021e1  mov     [rbx+8], rdx
0x1400021e5  lea     rax, [rbx+10h]
0x1400021e9  mov     rcx, rdi; rclsid
0x1400021ec  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x1400021f1  lea     r8d, [r9+4]; dwClsContext
0x1400021f5  call    cs:__imp_CoRegisterClassObject
0x1400021fb  mov     rbx, [rsp+38h+arg_0]
0x140002200  add     rsp, 30h
0x140002204  pop     rdi
0x140002205  retn
```
