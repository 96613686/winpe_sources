# CSyncServices::DeserializeFilterInfo(uchar const *,ulong,ISyncFilterInfo * *)

- ea: `0x18002cba0`
- end: `0x18002cc64`
- name: `?DeserializeFilterInfo@CSyncServices@@UEAAJPEBEKPEAPEAUISyncFilterInfo@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, const unsigned __int8 *, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002cba0`
- `0x18004b9fc`

## string_xrefs

- `0x18002cbdc`: `CSyncServices::DeserializeFilterInfo`
- `0x18002cc39`: `CSyncServices::DeserializeFilterInfo`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeFilterInfo(
        CSyncServices *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct ISyncFilterInfo **a4)
{
  PVOID *v8; // rcx
  struct IdParameters *v9; // rdx
  unsigned int v10; // ebx
  unsigned int v11; // eax

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeFilterInfo");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = (struct IdParameters *)*((_QWORD *)this + 6);
  v10 = -2147217407;
  if ( v9 )
  {
    v11 = FilterInfo::Deserialize(0, v9, a2, a3, a4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v10 = v11;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      21,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeFilterInfo",
      v10);
  return v10;
}

```

## disassembly

```asm
0x18002cba0  push    rbx
0x18002cba2  push    rbp
0x18002cba3  push    rsi
0x18002cba4  push    rdi
0x18002cba5  push    r14
0x18002cba7  push    r15
0x18002cba9  sub     rsp, 38h
0x18002cbad  mov     rsi, r9
0x18002cbb0  mov     ebp, r8d
0x18002cbb3  mov     r14, rdx
0x18002cbb6  mov     rdi, rcx
0x18002cbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbc0  lea     r15, WPP_GLOBAL_Control
0x18002cbc7  cmp     rcx, r15
0x18002cbca  jz      short loc_18002CBFB
0x18002cbcc  test    byte ptr [rcx+1Ch], 2
0x18002cbd0  jz      short loc_18002CBFB
0x18002cbd2  cmp     byte ptr [rcx+19h], 5
0x18002cbd6  jb      short loc_18002CBFB
0x18002cbd8  mov     rcx, [rcx+10h]
0x18002cbdc  lea     r9, aCsyncservicesD; "CSyncServices::DeserializeFilterInfo"
0x18002cbe3  mov     edx, 14h
0x18002cbe8  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cbef  call    WPP_SF_s
0x18002cbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbfb  mov     rdx, [rdi+30h]; struct IdParameters *
0x18002cbff  mov     ebx, 80041001h
0x18002cc04  test    rdx, rdx
0x18002cc07  jz      short loc_18002CC24
0x18002cc09  mov     r9d, ebp; unsigned int
0x18002cc0c  mov     [rsp+68h+var_48], rsi; struct ISyncFilterInfo **
0x18002cc11  mov     r8, r14; unsigned __int8 *
0x18002cc14  xor     ecx, ecx; struct ISyncFilterDeserializer *
0x18002cc16  call    ?Deserialize@FilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; FilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18002cc1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc22  mov     ebx, eax
0x18002cc24  cmp     rcx, r15
0x18002cc27  jz      short loc_18002CC55
0x18002cc29  test    byte ptr [rcx+1Ch], 2
0x18002cc2d  jz      short loc_18002CC55
0x18002cc2f  cmp     byte ptr [rcx+19h], 5
0x18002cc33  jb      short loc_18002CC55
0x18002cc35  mov     rcx, [rcx+10h]
0x18002cc39  lea     r9, aCsyncservicesD; "CSyncServices::DeserializeFilterInfo"
0x18002cc40  mov     edx, 15h
0x18002cc45  mov     dword ptr [rsp+68h+var_48], ebx
0x18002cc49  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cc50  call    WPP_SF_sD
0x18002cc55  mov     eax, ebx
0x18002cc57  add     rsp, 38h
0x18002cc5b  pop     r15
0x18002cc5d  pop     r14
0x18002cc5f  pop     rdi
0x18002cc60  pop     rsi
0x18002cc61  pop     rbp
0x18002cc62  pop     rbx
0x18002cc63  retn
```
