# CSyncServices::CreateFilterKeyMap(IFilterKeyMap * *)

- ea: `0x18002b850`
- end: `0x18002b951`
- name: `?CreateFilterKeyMap@CSyncServices@@UEAAJPEAPEAUIFilterKeyMap@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(struct IdParameters **this, struct IFilterKeyMap **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002ae24`
- `0x18002b850`
- `0x180094010`

## string_xrefs

- `0x18002b882`: `CSyncServices::CreateFilterKeyMap`
- `0x18002b92a`: `CSyncServices::CreateFilterKeyMap`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateFilterKeyMap(struct IdParameters **this, struct IFilterKeyMap **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  FilterKeyMap *v6; // rax
  FilterKeyMap *v7; // rax
  FilterKeyMap *v8; // rdi

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateFilterKeyMap");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( this[4] )
    {
      v6 = (FilterKeyMap *)SeAlloc(0x28u);
      if ( v6 && (v7 = FilterKeyMap::FilterKeyMap(v6, this[4]), (v8 = v7) != 0) )
      {
        v5 = (**(__int64 (__fastcall ***)(FilterKeyMap *, GUID *, struct IFilterKeyMap **))v7)(
               v7,
               &GUID_ca169652_07c6_4708_a3da_6e4eba8d2297,
               a2);
        (*(void (__fastcall **)(FilterKeyMap *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      else
      {
        v5 = -2147024882;
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v5 = -2147217407;
    }
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      69,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateFilterKeyMap",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18002b850  push    rbx
0x18002b852  push    rbp
0x18002b853  push    rsi
0x18002b854  push    rdi
0x18002b855  sub     rsp, 38h
0x18002b859  mov     rsi, rdx
0x18002b85c  mov     rbx, rcx
0x18002b85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b866  lea     rbp, WPP_GLOBAL_Control
0x18002b86d  cmp     rcx, rbp
0x18002b870  jz      short loc_18002B8A1
0x18002b872  test    byte ptr [rcx+1Ch], 2
0x18002b876  jz      short loc_18002B8A1
0x18002b878  cmp     byte ptr [rcx+19h], 5
0x18002b87c  jb      short loc_18002B8A1
0x18002b87e  mov     rcx, [rcx+10h]
0x18002b882  lea     r9, aCsyncservicesC_3; "CSyncServices::CreateFilterKeyMap"
0x18002b889  mov     edx, 44h ; 'D'
0x18002b88e  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b895  call    WPP_SF_s
0x18002b89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8a1  test    rsi, rsi
0x18002b8a4  jnz     short loc_18002B8AD
0x18002b8a6  mov     ebx, 80004003h
0x18002b8ab  jmp     short loc_18002B915
0x18002b8ad  cmp     qword ptr [rbx+20h], 0
0x18002b8b2  jnz     short loc_18002B8BB
0x18002b8b4  mov     ebx, 80041001h
0x18002b8b9  jmp     short loc_18002B915
0x18002b8bb  mov     ecx, 28h ; '('; unsigned __int64
0x18002b8c0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002b8c5  test    rax, rax
0x18002b8c8  jz      short loc_18002B909
0x18002b8ca  mov     rdx, [rbx+20h]; struct IdParameters *
0x18002b8ce  mov     rcx, rax; this
0x18002b8d1  call    ??0FilterKeyMap@@QEAA@PEAVIdParameters@@@Z; FilterKeyMap::FilterKeyMap(IdParameters *)
0x18002b8d6  mov     rdi, rax
0x18002b8d9  test    rax, rax
0x18002b8dc  jz      short loc_18002B909
0x18002b8de  mov     rax, [rax]
0x18002b8e1  lea     rdx, _GUID_ca169652_07c6_4708_a3da_6e4eba8d2297
0x18002b8e8  mov     r8, rsi
0x18002b8eb  mov     rcx, rdi
0x18002b8ee  mov     rax, [rax]
0x18002b8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8f6  mov     rcx, [rdi]
0x18002b8f9  mov     ebx, eax
0x18002b8fb  mov     rax, [rcx+10h]
0x18002b8ff  mov     rcx, rdi
0x18002b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b907  jmp     short loc_18002B90E
0x18002b909  mov     ebx, 8007000Eh
0x18002b90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b915  cmp     rcx, rbp
0x18002b918  jz      short loc_18002B946
0x18002b91a  test    byte ptr [rcx+1Ch], 2
0x18002b91e  jz      short loc_18002B946
0x18002b920  cmp     byte ptr [rcx+19h], 5
0x18002b924  jb      short loc_18002B946
0x18002b926  mov     rcx, [rcx+10h]
0x18002b92a  lea     r9, aCsyncservicesC_3; "CSyncServices::CreateFilterKeyMap"
0x18002b931  mov     edx, 45h ; 'E'
0x18002b936  mov     [rsp+58h+var_38], ebx
0x18002b93a  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b941  call    WPP_SF_sD
0x18002b946  mov     eax, ebx
0x18002b948  add     rsp, 38h
0x18002b94c  pop     rdi
0x18002b94d  pop     rsi
0x18002b94e  pop     rbp
0x18002b94f  pop     rbx
0x18002b950  retn
```
