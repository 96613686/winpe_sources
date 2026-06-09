# MbbUtilWwanToMbbContextType(_WWAN_CONTEXT_TYPE,_GUID *)

- ea: `0x140021818`
- end: `0x1400219a7`
- name: `?MbbUtilWwanToMbbContextType@@YAXW4_WWAN_CONTEXT_TYPE@@PEAU_GUID@@@Z`
- size: `399`
- prototype: `void __fastcall(int, struct _GUID *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c400`
- `0x14001cbb0`
- `0x14001cd78`
- `0x14001d05c`
- `0x14001f834`
- `0x140021d8c`

## callees

- `0x140021818`

## pseudocode

```c
void __fastcall MbbUtilWwanToMbbContextType(int a1, struct _GUID *a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  unsigned __int64 v7; // rax
  unsigned int v8; // ecx
  __int16 v9; // dx
  __int16 v10; // r8
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx

  if ( a1 > 6 )
  {
    v11 = a1 - 7;
    if ( !v11 )
    {
      v7 = 0xA9AC8953D3D12496uLL;
      v8 = 1181902436;
      v9 = 29289;
      v10 = 27590;
      goto LABEL_24;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v7 = 0xD697D6073AB52594uLL;
      v8 = 560008449;
      v9 = 12404;
      v10 = 19406;
      goto LABEL_24;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v7 = 0x4B1FD1CFABF039A2LL;
      v8 = 1602112558;
      v9 = -6133;
      v10 = 16553;
      goto LABEL_24;
    }
    if ( v13 == 1 )
    {
      v7 = 0xEEB27BA310738C9AuLL;
      v8 = 1960348221;
      v9 = -8259;
      v10 = 18329;
      goto LABEL_24;
    }
    goto LABEL_19;
  }
  if ( a1 == 6 )
  {
    v7 = 0x1772A287F6ACC0A8LL;
    v8 = -1289280362;
    v9 = -21396;
    v10 = 16939;
    goto LABEL_24;
  }
  if ( !a1 )
    goto LABEL_19;
  v3 = a1 - 1;
  if ( !v3 )
  {
    v7 = 0x7E2A5E7E6E656B73LL;
    v8 = 2120100478;
    v9 = 20079;
    v10 = 29298;
    goto LABEL_24;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v7 = 0xA0F78D3141CAAC83uLL;
    v8 = -1684046914;
    v9 = -30382;
    v10 = 17591;
    goto LABEL_24;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v7 = 0xB202BC8F58A8CA8CuLL;
    v8 = -2003729772;
    v9 = 3828;
    v10 = 17302;
    goto LABEL_24;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = 0xCCAA7A0CEFC5919AuLL;
    v8 = 94545686;
    v9 = 31796;
    v10 = 19277;
    goto LABEL_24;
  }
  if ( v6 != 1 )
  {
LABEL_19:
    v7 = 0x54FB419686C55EB3LL;
    v8 = -1270909556;
    v9 = -23200;
    v10 = 19270;
    goto LABEL_24;
  }
  v7 = 0x10DF710E3153B7B8LL;
  v8 = -1672919742;
  v9 = -23493;
  v10 = 20133;
LABEL_24:
  a2->Data1 = _byteswap_ulong(v8);
  a2->Data2 = __ROR2__(v9, 8);
  a2->Data3 = __ROR2__(v10, 8);
  *(_QWORD *)a2->Data4 = v7;
}

```

## disassembly

```asm
0x140021818  mov     r9, rdx
0x14002181b  cmp     ecx, 6
0x14002181e  jg      loc_1400218FB
0x140021824  jz      loc_1400218DF
0x14002182a  test    ecx, ecx
0x14002182c  jz      loc_14002190F
0x140021832  sub     ecx, 1
0x140021835  jz      loc_1400218C3
0x14002183b  sub     ecx, 1
0x14002183e  jz      short loc_1400218A7
0x140021840  sub     ecx, 1
0x140021843  jz      short loc_14002188B
0x140021845  sub     ecx, 1
0x140021848  jz      short loc_14002186F
0x14002184a  cmp     ecx, 1
0x14002184d  jnz     loc_14002190F
0x140021853  mov     rax, cs:qword_14004E8B8
0x14002185a  mov     ecx, 9C494542h
0x14002185f  mov     edx, 0A43Bh
0x140021864  mov     r8d, 4EA5h
0x14002186a  jmp     loc_14002198A
0x14002186f  mov     rax, cs:qword_14004E870
0x140021876  mov     ecx, 5A2A716h
0x14002187b  mov     edx, 7C34h
0x140021880  mov     r8d, 4B4Dh
0x140021886  jmp     loc_14002198A
0x14002188b  mov     rax, cs:qword_14004E7B8
0x140021892  mov     ecx, 88918294h
0x140021897  mov     edx, 0EF4h
0x14002189c  mov     r8d, 4396h
0x1400218a2  jmp     loc_14002198A
0x1400218a7  mov     rax, cs:qword_14004E7E8
0x1400218ae  mov     ecx, 9B9F7BBEh
0x1400218b3  mov     edx, 8952h
0x1400218b8  mov     r8d, 44B7h
0x1400218be  jmp     loc_14002198A
0x1400218c3  mov     rax, cs:qword_14004E7F8
0x1400218ca  mov     ecx, 7E5E2A7Eh
0x1400218cf  mov     edx, 4E6Fh
0x1400218d4  mov     r8d, 7272h
0x1400218da  jmp     loc_14002198A
0x1400218df  mov     rax, cs:qword_14004E768
0x1400218e6  mov     ecx, 0B3272496h
0x1400218eb  mov     edx, 0AC6Ch
0x1400218f0  mov     r8d, 422Bh
0x1400218f6  jmp     loc_14002198A
0x1400218fb  sub     ecx, 7
0x1400218fe  jz      short loc_140021973
0x140021900  sub     ecx, 1
0x140021903  jz      short loc_14002195A
0x140021905  sub     ecx, 1
0x140021908  jz      short loc_140021941
0x14002190a  cmp     ecx, 1
0x14002190d  jz      short loc_140021928
0x14002190f  mov     rax, cs:qword_14004E950
0x140021916  mov     ecx, 0B43F758Ch
0x14002191b  mov     edx, 0A560h
0x140021920  mov     r8d, 4B46h
0x140021926  jmp     short loc_14002198A
0x140021928  mov     rax, cs:qword_14004E930
0x14002192f  mov     ecx, 74D88A3Dh
0x140021934  mov     edx, 0DFBDh
0x140021939  mov     r8d, 4799h
0x14002193f  jmp     short loc_14002198A
0x140021941  mov     rax, cs:qword_14004E9E0
0x140021948  mov     ecx, 5F7E4C2Eh
0x14002194d  mov     edx, 0E80Bh
0x140021952  mov     r8d, 40A9h
0x140021958  jmp     short loc_14002198A
0x14002195a  mov     rax, cs:qword_14004E880
0x140021961  mov     ecx, 21610D01h
0x140021966  mov     edx, 3074h
0x14002196b  mov     r8d, 4BCEh
0x140021971  jmp     short loc_14002198A
0x140021973  mov     rax, cs:qword_14004E838
0x14002197a  mov     ecx, 46726664h
0x14002197f  mov     edx, 7269h
0x140021984  mov     r8d, 6BC6h
0x14002198a  bswap   ecx
0x14002198c  ror     dx, 8
0x140021990  ror     r8w, 8
0x140021995  mov     [r9], ecx
0x140021998  mov     [r9+4], dx
0x14002199d  mov     [r9+6], r8w
0x1400219a2  mov     [r9+8], rax
0x1400219a6  retn
```
