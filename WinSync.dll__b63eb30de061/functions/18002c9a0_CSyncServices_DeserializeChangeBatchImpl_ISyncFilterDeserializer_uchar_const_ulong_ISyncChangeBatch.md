# CSyncServices::DeserializeChangeBatchImpl(ISyncFilterDeserializer *,uchar const *,ulong,ISyncChangeBatch * *)

- ea: `0x18002c9a0`
- end: `0x18002cae1`
- name: `?DeserializeChangeBatchImpl@CSyncServices@@AEAAJPEAUISyncFilterDeserializer@@PEBEKPEAPEAUISyncChangeBatch@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct ISyncFilterDeserializer *, const unsigned __int8 *, unsigned int, struct ISyncChangeBatch **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002c960`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002c9a0`
- `0x18004e754`
- `0x180094010`

## string_xrefs

- `0x18002c9e4`: `CSyncServices::DeserializeChangeBatchImpl`
- `0x18002caaf`: `CSyncServices::DeserializeChangeBatchImpl`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeChangeBatchImpl(
        CSyncServices *this,
        struct ISyncFilterDeserializer *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct ISyncChangeBatch **a5)
{
  PVOID *v8; // rcx
  unsigned __int64 v9; // rdx
  int v10; // ebx
  struct CSyncChangeBatch *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = (struct CSyncChangeBatch *)a2;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeChangeBatchImpl");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = *((_QWORD *)this + 7);
  v10 = -2147217407;
  if ( v9 )
  {
    v10 = -2147467261;
    if ( a5 )
    {
      v12 = 0;
      v10 = CSyncChangeBatch::Deserialize(
              0,
              v9,
              (struct IProviderSyncServices *)(((unsigned __int64)this + 16) & -(__int64)(this != 0)),
              a3,
              a4,
              &v12);
      if ( v10 >= 0 )
      {
        v10 = (**(__int64 (__fastcall ***)(struct CSyncChangeBatch *, GUID *, struct ISyncChangeBatch **))v12)(
                v12,
                &GUID_70c64dee_380f_4c2e_8f70_31c55bd5f9b3,
                a5);
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
      43,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeChangeBatchImpl",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002c9a0  mov     [rsp+arg_0], rbx
0x18002c9a5  mov     [rsp+arg_10], rbp
0x18002c9aa  mov     [rsp+arg_8], rdx
0x18002c9af  push    rdi
0x18002c9b0  push    r14
0x18002c9b2  push    r15
0x18002c9b4  sub     rsp, 30h
0x18002c9b8  mov     ebp, r9d
0x18002c9bb  mov     r14, r8
0x18002c9be  mov     rdi, rcx
0x18002c9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9c8  lea     r15, WPP_GLOBAL_Control
0x18002c9cf  cmp     rcx, r15
0x18002c9d2  jz      short loc_18002CA03
0x18002c9d4  test    byte ptr [rcx+1Ch], 2
0x18002c9d8  jz      short loc_18002CA03
0x18002c9da  cmp     byte ptr [rcx+19h], 5
0x18002c9de  jb      short loc_18002CA03
0x18002c9e0  mov     rcx, [rcx+10h]
0x18002c9e4  lea     r9, aCsyncservicesD_1; "CSyncServices::DeserializeChangeBatchIm"...
0x18002c9eb  mov     edx, 2Ah ; '*'
0x18002c9f0  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c9f7  call    WPP_SF_s
0x18002c9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca03  mov     rdx, [rdi+38h]; struct IdParameters *
0x18002ca07  mov     ebx, 80041001h
0x18002ca0c  test    rdx, rdx
0x18002ca0f  jz      loc_18002CA9A
0x18002ca15  cmp     [rsp+48h+arg_20], 0
0x18002ca1b  mov     ebx, 80004003h
0x18002ca20  jz      short loc_18002CA9A
0x18002ca22  lea     rax, [rdi+10h]
0x18002ca26  mov     [rsp+48h+arg_8], 0
0x18002ca2f  neg     rdi
0x18002ca32  mov     r9, r14; unsigned __int8 *
0x18002ca35  sbb     r8, r8
0x18002ca38  xor     ecx, ecx; struct ISyncFilterDeserializer *
0x18002ca3a  and     r8, rax; struct IProviderSyncServices *
0x18002ca3d  lea     rax, [rsp+48h+arg_8]
0x18002ca42  mov     [rsp+48h+var_20], rax; struct CSyncChangeBatch **
0x18002ca47  mov     [rsp+48h+var_28], ebp; unsigned int
0x18002ca4b  call    ?Deserialize@CSyncChangeBatch@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEAUIProviderSyncServices@@PEBEJPEAPEAV1@@Z; CSyncChangeBatch::Deserialize(ISyncFilterDeserializer *,IdParameters *,IProviderSyncServices *,uchar const *,long,CSyncChangeBatch * *)
0x18002ca50  mov     ebx, eax
0x18002ca52  test    eax, eax
0x18002ca54  js      short loc_18002CA93
0x18002ca56  mov     rcx, [rsp+48h+arg_8]
0x18002ca5b  lea     rdx, _GUID_70c64dee_380f_4c2e_8f70_31c55bd5f9b3
0x18002ca62  mov     r8, [rsp+48h+arg_20]
0x18002ca67  mov     rax, [rcx]
0x18002ca6a  mov     rax, [rax]
0x18002ca6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca72  mov     rcx, [rsp+48h+arg_8]
0x18002ca77  mov     ebx, eax
0x18002ca79  mov     rax, [rcx]
0x18002ca7c  mov     rax, [rax+10h]
0x18002ca80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca85  cmp     ebx, 80004002h
0x18002ca8b  mov     eax, 8004100Ch
0x18002ca90  cmovz   ebx, eax
0x18002ca93  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca9a  cmp     rcx, r15
0x18002ca9d  jz      short loc_18002CACB
0x18002ca9f  test    byte ptr [rcx+1Ch], 2
0x18002caa3  jz      short loc_18002CACB
0x18002caa5  cmp     byte ptr [rcx+19h], 5
0x18002caa9  jb      short loc_18002CACB
0x18002caab  mov     rcx, [rcx+10h]
0x18002caaf  lea     r9, aCsyncservicesD_1; "CSyncServices::DeserializeChangeBatchIm"...
0x18002cab6  mov     edx, 2Bh ; '+'
0x18002cabb  mov     [rsp+48h+var_28], ebx
0x18002cabf  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002cac6  call    WPP_SF_sD
0x18002cacb  mov     rbp, [rsp+48h+arg_10]
0x18002cad0  mov     eax, ebx
0x18002cad2  mov     rbx, [rsp+48h+arg_0]
0x18002cad7  add     rsp, 30h
0x18002cadb  pop     r15
0x18002cadd  pop     r14
0x18002cadf  pop     rdi
0x18002cae0  retn
```
