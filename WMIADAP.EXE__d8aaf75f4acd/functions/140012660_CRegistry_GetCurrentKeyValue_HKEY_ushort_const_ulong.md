# CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,ulong &)

- ea: `0x140012660`
- end: `0x140012717`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAK@Z`
- size: `183`
- prototype: `__int64 __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012b60`
- `0x140012e00`

## callees

- `0x14000298c`
- `0x140012660`
- `0x140012bc0`

## import_xrefs

- `msvcrt!atol` at `0x1400126df`
- `msvcrt!atol` at `0x1400126df`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400126ea`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400126ea`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012688`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012688`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  char *v8; // rax
  char *v9; // rbx
  unsigned int CurrentRawKeyValue; // esi
  int v11; // eax
  unsigned int v13; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-34h] BYREF
  int pExceptionObject; // [rsp+38h] [rbp-30h] BYREF

  v13 = 0;
  v14 = 256;
  v8 = (char *)CWin32DefaultArena::WbemMemAlloc(0x100u);
  v9 = v8;
  if ( !v8 )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  CurrentRawKeyValue = CRegistry::GetCurrentRawKeyValue(this, a2, a3, v8, &v13, &v14);
  if ( !CurrentRawKeyValue )
  {
    if ( v13 == 1 )
    {
      v11 = atol(v9);
    }
    else
    {
      if ( v13 != 4 )
      {
        *a4 = 0;
        CurrentRawKeyValue = -2147221165;
        goto LABEL_9;
      }
      v11 = *(_DWORD *)v9;
    }
    *a4 = v11;
  }
LABEL_9:
  CWin32DefaultArena::WbemMemFree(v9);
  return CurrentRawKeyValue;
}

```

## disassembly

```asm
0x140012660  push    rbx
0x140012662  push    rbp
0x140012663  push    rsi
0x140012664  push    rdi
0x140012665  push    r14
0x140012667  sub     rsp, 40h
0x14001266b  mov     r14, rcx
0x14001266e  mov     [rsp+68h+var_38], 0
0x140012676  mov     ecx, 100h
0x14001267b  mov     rdi, r9
0x14001267e  mov     [rsp+68h+var_34], ecx
0x140012682  mov     rsi, r8
0x140012685  mov     rbp, rdx
0x140012688  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14001268e  mov     rbx, rax
0x140012691  test    rax, rax
0x140012694  jz      short loc_1400126FD
0x140012696  lea     rax, [rsp+68h+var_34]
0x14001269b  mov     r9, rbx; void *
0x14001269e  mov     [rsp+68h+var_40], rax; unsigned int *
0x1400126a3  mov     r8, rsi; unsigned __int16 *
0x1400126a6  lea     rax, [rsp+68h+var_38]
0x1400126ab  mov     rdx, rbp; HKEY
0x1400126ae  mov     rcx, r14; this
0x1400126b1  mov     [rsp+68h+var_48], rax; unsigned int *
0x1400126b6  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x1400126bb  mov     esi, eax
0x1400126bd  test    eax, eax
0x1400126bf  jnz     short loc_1400126E7
0x1400126c1  mov     ecx, [rsp+68h+var_38]
0x1400126c5  sub     ecx, 1
0x1400126c8  jz      short loc_1400126DC
0x1400126ca  cmp     ecx, 3
0x1400126cd  jz      short loc_1400126D8
0x1400126cf  mov     [rdi], eax
0x1400126d1  mov     esi, 80040153h
0x1400126d6  jmp     short loc_1400126E7
0x1400126d8  mov     eax, [rbx]
0x1400126da  jmp     short loc_1400126E5
0x1400126dc  mov     rcx, rbx; String
0x1400126df  call    cs:__imp_atol
0x1400126e5  mov     [rdi], eax
0x1400126e7  mov     rcx, rbx
0x1400126ea  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400126f0  mov     eax, esi
0x1400126f2  add     rsp, 40h
0x1400126f6  pop     r14
0x1400126f8  pop     rdi
0x1400126f9  pop     rsi
0x1400126fa  pop     rbp
0x1400126fb  pop     rbx
0x1400126fc  retn
0x1400126fd  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x140012704  mov     [rsp+68h+pExceptionObject], 0
0x14001270c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140012711  call    _CxxThrowException_0
```
