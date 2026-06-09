# CBcdObject::CreateNew(IWbemServices *,IWbemClassObject *,CBcdObject * *)

- ea: `0x18000a4f0`
- end: `0x18000a5a5`
- name: `?CreateNew@CBcdObject@@KAJPEAUIWbemServices@@PEAUIWbemClassObject@@PEAPEAV1@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemClassObject *, struct CBcdObject **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000c4d0`

## callees

- `0x1800015c4`
- `0x180009bd0`
- `0x18000a4f0`
- `0x18000b094`
- `0x18000bb80`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CBcdObject::CreateNew(struct IWbemServices *a1, struct IWbemClassObject *a2, struct CBcdObject **a3)
{
  CBcdObject *v6; // rax
  CBcdObject *v7; // rbx
  int v8; // edi

  v6 = (CBcdObject *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    v7 = CBcdObject::CBcdObject(v6);
  else
    v7 = 0;
  if ( v7 )
  {
    v8 = CBcdObject::FillInProperties(v7, a2);
    if ( v8 >= 0 )
    {
      v8 = CBcdWmiWrapper::InitializeInstance(v7, a1, a2);
      if ( v8 >= 0 )
      {
        *a3 = v7;
        v7 = 0;
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  if ( v7 )
    (**(void (__fastcall ***)(CBcdObject *, __int64))v7)(v7, 1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a4f0  push    rbx
0x18000a4f2  push    rsi
0x18000a4f3  push    rdi
0x18000a4f4  push    r14
0x18000a4f6  push    r15
0x18000a4f8  sub     rsp, 30h
0x18000a4fc  mov     r14, r8
0x18000a4ff  mov     rsi, rdx
0x18000a502  mov     r15, rcx
0x18000a505  mov     [rsp+58h+var_30], 0
0x18000a50e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a515  mov     ecx, 40h ; '@'; unsigned __int64
0x18000a51a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a51f  test    rax, rax
0x18000a522  jz      short loc_18000A531
0x18000a524  mov     rcx, rax; this
0x18000a527  call    ??0CBcdObject@@IEAA@XZ; CBcdObject::CBcdObject(void)
0x18000a52c  mov     rbx, rax
0x18000a52f  jmp     short loc_18000A533
0x18000a531  xor     ebx, ebx
0x18000a533  mov     [rsp+58h+var_30], rbx
0x18000a538  test    rbx, rbx
0x18000a53b  jnz     short loc_18000A548
0x18000a53d  mov     edi, 8007000Eh
0x18000a542  mov     [rsp+58h+var_38], edi
0x18000a546  jmp     short loc_18000A57F
0x18000a548  mov     rdx, rsi; struct IWbemClassObject *
0x18000a54b  mov     rcx, rbx; this
0x18000a54e  call    ?FillInProperties@CBcdObject@@IEAAJPEAUIWbemClassObject@@@Z; CBcdObject::FillInProperties(IWbemClassObject *)
0x18000a553  mov     edi, eax
0x18000a555  mov     [rsp+58h+var_38], eax
0x18000a559  test    eax, eax
0x18000a55b  js      short loc_18000A57F
0x18000a55d  mov     r8, rsi; struct IWbemClassObject *
0x18000a560  mov     rdx, r15; struct IWbemServices *
0x18000a563  mov     rcx, rbx; this
0x18000a566  call    ?InitializeInstance@CBcdWmiWrapper@@IEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CBcdWmiWrapper::InitializeInstance(IWbemServices *,IWbemClassObject *)
0x18000a56b  mov     edi, eax
0x18000a56d  mov     [rsp+58h+var_38], eax
0x18000a571  test    eax, eax
0x18000a573  js      short loc_18000A57F
0x18000a575  mov     [r14], rbx
0x18000a578  xor     ebx, ebx
0x18000a57a  mov     [rsp+58h+var_30], rbx
0x18000a57f  test    rbx, rbx
0x18000a582  jz      short loc_18000A597
0x18000a584  mov     rax, [rbx]
0x18000a587  mov     edx, 1
0x18000a58c  mov     rcx, rbx
0x18000a58f  mov     rax, [rax]
0x18000a592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a597  mov     eax, edi
0x18000a599  add     rsp, 30h
0x18000a59d  pop     r15
0x18000a59f  pop     r14
0x18000a5a1  pop     rdi
0x18000a5a2  pop     rsi
0x18000a5a3  pop     rbx
0x18000a5a4  retn
0x180013a20  push    rbp
0x180013a22  sub     rsp, 20h
0x180013a26  mov     rbp, rdx
0x180013a29  mov     rcx, [rbp+28h]
0x180013a2d  test    rcx, rcx
0x180013a30  jz      short loc_180013A43
0x180013a32  mov     rax, [rcx]
0x180013a35  mov     edx, 1
0x180013a3a  mov     rax, [rax]
0x180013a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a42  nop
0x180013a43  add     rsp, 20h
0x180013a47  pop     rbp
0x180013a48  retn
```
