# CSyncServices::DeserializeFullEnumerationChangeBatch(uchar const *,ulong,ISyncFullEnumerationChangeBatch * *)

- ea: `0x18002ce70`
- end: `0x18002cfa1`
- name: `?DeserializeFullEnumerationChangeBatch@CSyncServices@@UEAAJPEBEKPEAPEAUISyncFullEnumerationChangeBatch@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, const unsigned __int8 *, unsigned int, struct ISyncFullEnumerationChangeBatch **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002cfb0`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002ce70`
- `0x18004e754`
- `0x180094010`

## string_xrefs

- `0x18002ceac`: `CSyncServices::DeserializeFullEnumerationChangeBatch`
- `0x18002cf76`: `CSyncServices::DeserializeFullEnumerationChangeBatch`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeFullEnumerationChangeBatch(
        CSyncServices *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct ISyncFullEnumerationChangeBatch **a4)
{
  PVOID *v8; // rcx
  unsigned __int64 v9; // rdx
  int v10; // ebx
  struct CSyncChangeBatch *v12; // [rsp+70h] [rbp+8h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeFullEnumerationChangeBatch");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = *((_QWORD *)this + 6);
  v10 = -2147217407;
  if ( v9 )
  {
    v10 = -2147467261;
    if ( a4 )
    {
      v12 = 0;
      v10 = CSyncChangeBatch::Deserialize(
              0,
              v9,
              (struct IProviderSyncServices *)(((unsigned __int64)this + 8) & -(__int64)(this != (CSyncServices *)8)),
              a2,
              a3,
              &v12);
      if ( v10 >= 0 )
      {
        v10 = (**(__int64 (__fastcall ***)(struct CSyncChangeBatch *, GUID *, struct ISyncFullEnumerationChangeBatch **))v12)(
                v12,
                &GUID_ef64197d_4f44_4ea2_b355_4524713e3bed,
                a4);
        (*(void (__fastcall **)(struct CSyncChangeBatch *))(*(_QWORD *)v12 + 16LL))(v12);
        if ( v10 == -2147467262 )
          v10 = -2147217396;
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      45,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeFullEnumerationChangeBatch",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002ce70  push    rbx
0x18002ce72  push    rbp
0x18002ce73  push    rsi
0x18002ce74  push    rdi
0x18002ce75  push    r14
0x18002ce77  push    r15
0x18002ce79  sub     rsp, 38h
0x18002ce7d  mov     rsi, r9
0x18002ce80  mov     ebp, r8d
0x18002ce83  mov     r14, rdx
0x18002ce86  mov     rdi, rcx
0x18002ce89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce90  lea     r15, WPP_GLOBAL_Control
0x18002ce97  cmp     rcx, r15
0x18002ce9a  jz      short loc_18002CECB
0x18002ce9c  test    byte ptr [rcx+1Ch], 2
0x18002cea0  jz      short loc_18002CECB
0x18002cea2  cmp     byte ptr [rcx+19h], 5
0x18002cea6  jb      short loc_18002CECB
0x18002cea8  mov     rcx, [rcx+10h]
0x18002ceac  lea     r9, aCsyncservicesD_0; "CSyncServices::DeserializeFullEnumerati"...
0x18002ceb3  mov     edx, 2Ch ; ','
0x18002ceb8  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cebf  call    WPP_SF_s
0x18002cec4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cecb  mov     rdx, [rdi+30h]; struct IdParameters *
0x18002cecf  mov     ebx, 80041001h
0x18002ced4  test    rdx, rdx
0x18002ced7  jz      loc_18002CF61
0x18002cedd  mov     ebx, 80004003h
0x18002cee2  test    rsi, rsi
0x18002cee5  jz      short loc_18002CF61
0x18002cee7  lea     rcx, [rdi+8]
0x18002ceeb  mov     [rsp+68h+arg_0], 0
0x18002cef4  lea     rax, [rdi-8]
0x18002cef8  mov     r9, r14; unsigned __int8 *
0x18002cefb  neg     rax
0x18002cefe  lea     rax, [rsp+68h+arg_0]
0x18002cf03  sbb     r8, r8
0x18002cf06  mov     [rsp+68h+var_40], rax; struct CSyncChangeBatch **
0x18002cf0b  and     r8, rcx; struct IProviderSyncServices *
0x18002cf0e  mov     [rsp+68h+var_48], ebp; unsigned int
0x18002cf12  xor     ecx, ecx; struct ISyncFilterDeserializer *
0x18002cf14  call    ?Deserialize@CSyncChangeBatch@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEAUIProviderSyncServices@@PEBEJPEAPEAV1@@Z; CSyncChangeBatch::Deserialize(ISyncFilterDeserializer *,IdParameters *,IProviderSyncServices *,uchar const *,long,CSyncChangeBatch * *)
0x18002cf19  mov     ebx, eax
0x18002cf1b  test    eax, eax
0x18002cf1d  js      short loc_18002CF5A
0x18002cf1f  mov     rcx, [rsp+68h+arg_0]
0x18002cf24  lea     rdx, _GUID_ef64197d_4f44_4ea2_b355_4524713e3bed
0x18002cf2b  mov     r8, rsi
0x18002cf2e  mov     rax, [rcx]
0x18002cf31  mov     rax, [rax]
0x18002cf34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf39  mov     rcx, [rsp+68h+arg_0]
0x18002cf3e  mov     ebx, eax
0x18002cf40  mov     rax, [rcx]
0x18002cf43  mov     rax, [rax+10h]
0x18002cf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf4c  cmp     ebx, 80004002h
0x18002cf52  mov     eax, 8004100Ch
0x18002cf57  cmovz   ebx, eax
0x18002cf5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf61  cmp     rcx, r15
0x18002cf64  jz      short loc_18002CF92
0x18002cf66  test    byte ptr [rcx+1Ch], 2
0x18002cf6a  jz      short loc_18002CF92
0x18002cf6c  cmp     byte ptr [rcx+19h], 5
0x18002cf70  jb      short loc_18002CF92
0x18002cf72  mov     rcx, [rcx+10h]
0x18002cf76  lea     r9, aCsyncservicesD_0; "CSyncServices::DeserializeFullEnumerati"...
0x18002cf7d  mov     edx, 2Dh ; '-'
0x18002cf82  mov     [rsp+68h+var_48], ebx
0x18002cf86  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cf8d  call    WPP_SF_sD
0x18002cf92  mov     eax, ebx
0x18002cf94  add     rsp, 38h
0x18002cf98  pop     r15
0x18002cf9a  pop     r14
0x18002cf9c  pop     rdi
0x18002cf9d  pop     rsi
0x18002cf9e  pop     rbp
0x18002cf9f  pop     rbx
0x18002cfa0  retn
```
