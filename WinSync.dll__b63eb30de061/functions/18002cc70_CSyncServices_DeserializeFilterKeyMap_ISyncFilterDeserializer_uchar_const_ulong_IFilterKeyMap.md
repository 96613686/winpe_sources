# CSyncServices::DeserializeFilterKeyMap(ISyncFilterDeserializer *,uchar const *,ulong,IFilterKeyMap * *)

- ea: `0x18002cc70`
- end: `0x18002cd3b`
- name: `?DeserializeFilterKeyMap@CSyncServices@@UEAAJPEAUISyncFilterDeserializer@@PEBEKPEAPEAUIFilterKeyMap@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(CSyncServices *this, struct ISyncFilterDeserializer *, const unsigned __int8 *, unsigned int, struct IFilterKeyMap **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002cc70`
- `0x18005f1c8`

## string_xrefs

- `0x18002ccaa`: `CSyncServices::DeserializeFilterKeyMap`
- `0x18002cd12`: `CSyncServices::DeserializeFilterKeyMap`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeFilterKeyMap(
        CSyncServices *this,
        struct ISyncFilterDeserializer *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct IFilterKeyMap **a5)
{
  PVOID *v9; // rcx
  struct IdParameters *v10; // rdx
  unsigned int v11; // ebx
  unsigned int v12; // eax

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeFilterKeyMap");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = (struct IdParameters *)*((_QWORD *)this + 4);
  if ( v10 )
  {
    v12 = FilterKeyMap::Deserialize(a2, v10, a3, a4, a5);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v11 = v12;
  }
  else
  {
    v11 = -2147217407;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      71,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeFilterKeyMap",
      v11);
  return v11;
}

```

## disassembly

```asm
0x18002cc70  push    rbx
0x18002cc72  push    rbp
0x18002cc73  push    rsi
0x18002cc74  push    rdi
0x18002cc75  push    r14
0x18002cc77  sub     rsp, 30h
0x18002cc7b  mov     edi, r9d
0x18002cc7e  mov     rsi, r8
0x18002cc81  mov     rbp, rdx
0x18002cc84  mov     rbx, rcx
0x18002cc87  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc8e  lea     r14, WPP_GLOBAL_Control
0x18002cc95  cmp     rcx, r14
0x18002cc98  jz      short loc_18002CCC9
0x18002cc9a  test    byte ptr [rcx+1Ch], 2
0x18002cc9e  jz      short loc_18002CCC9
0x18002cca0  cmp     byte ptr [rcx+19h], 5
0x18002cca4  jb      short loc_18002CCC9
0x18002cca6  mov     rcx, [rcx+10h]
0x18002ccaa  lea     r9, aCsyncservicesD_3; "CSyncServices::DeserializeFilterKeyMap"
0x18002ccb1  mov     edx, 46h ; 'F'
0x18002ccb6  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002ccbd  call    WPP_SF_s
0x18002ccc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccc9  mov     rdx, [rbx+20h]; struct IdParameters *
0x18002cccd  test    rdx, rdx
0x18002ccd0  jnz     short loc_18002CCD9
0x18002ccd2  mov     ebx, 80041001h
0x18002ccd7  jmp     short loc_18002CCFD
0x18002ccd9  mov     rax, [rsp+58h+arg_20]
0x18002cce1  mov     r9d, edi; unsigned int
0x18002cce4  mov     r8, rsi; unsigned __int8 *
0x18002cce7  mov     [rsp+58h+var_38], rax; struct IFilterKeyMap **
0x18002ccec  mov     rcx, rbp; struct ISyncFilterDeserializer *
0x18002ccef  call    ?Deserialize@FilterKeyMap@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUIFilterKeyMap@@@Z; FilterKeyMap::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,IFilterKeyMap * *)
0x18002ccf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccfb  mov     ebx, eax
0x18002ccfd  cmp     rcx, r14
0x18002cd00  jz      short loc_18002CD2E
0x18002cd02  test    byte ptr [rcx+1Ch], 2
0x18002cd06  jz      short loc_18002CD2E
0x18002cd08  cmp     byte ptr [rcx+19h], 5
0x18002cd0c  jb      short loc_18002CD2E
0x18002cd0e  mov     rcx, [rcx+10h]
0x18002cd12  lea     r9, aCsyncservicesD_3; "CSyncServices::DeserializeFilterKeyMap"
0x18002cd19  mov     edx, 47h ; 'G'
0x18002cd1e  mov     dword ptr [rsp+58h+var_38], ebx
0x18002cd22  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cd29  call    WPP_SF_sD
0x18002cd2e  mov     eax, ebx
0x18002cd30  add     rsp, 30h
0x18002cd34  pop     r14
0x18002cd36  pop     rdi
0x18002cd37  pop     rsi
0x18002cd38  pop     rbp
0x18002cd39  pop     rbx
0x18002cd3a  retn
```
