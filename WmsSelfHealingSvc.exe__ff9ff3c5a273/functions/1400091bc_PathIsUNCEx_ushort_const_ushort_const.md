# PathIsUNCEx(ushort const *,ushort const * *)

- ea: `0x1400091bc`
- end: `0x140009286`
- name: `?PathIsUNCEx@@YAHPEBGPEAPEBG@Z`
- size: `202`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008974`
- `0x140009000`

## callees

- `0x1400091bc`
- `0x14000928c`

## pseudocode

```c
_BOOL8 __fastcall PathIsUNCEx(const unsigned __int16 *a1, const unsigned __int16 **a2)
{
  BOOL v2; // r8d
  int IsVolumeGUIDWorker; // eax
  __int64 v6; // rdx
  int v7; // esi
  const wchar_t *v8; // r10
  const unsigned __int16 *v9; // r11
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  int v13; // r9d

  v2 = 0;
  if ( *(_DWORD *)a1 != 6029404 )
    return v2;
  if ( a1[2] != 63 )
  {
    IsVolumeGUIDWorker = PathIsVolumeGUIDWorker(a1);
    v6 = IsVolumeGUIDWorker == 0 ? 2 : 0;
    v2 = IsVolumeGUIDWorker == 0;
    if ( IsVolumeGUIDWorker )
      return v2;
    goto LABEL_15;
  }
  v7 = 5;
  v8 = L"\\UNC\\";
  v9 = a1 + 3;
  do
  {
    v10 = *v9;
    v11 = v10 + 32;
    if ( (unsigned int)(v10 - 65) > 0x19 )
      v11 = *v9;
    v12 = *v8;
    v13 = v12 + 32;
    if ( (unsigned int)(v12 - 65) > 0x19 )
      v13 = *v8;
    if ( !--v7 )
      break;
    if ( !v11 )
      break;
    ++v9;
    ++v8;
  }
  while ( v11 == v13 );
  if ( v11 == v13 )
  {
    v6 = 8;
    v2 = 1;
LABEL_15:
    if ( a2 )
      *a2 = &a1[v6];
  }
  return v2;
}

```

## disassembly

```asm
0x1400091bc  mov     [rsp+arg_0], rbx
0x1400091c1  mov     [rsp+arg_8], rsi
0x1400091c6  push    rdi
0x1400091c7  sub     rsp, 20h
0x1400091cb  xor     r8d, r8d
0x1400091ce  mov     rdi, rdx
0x1400091d1  cmp     word ptr [rcx], 5Ch ; '\'
0x1400091d5  mov     rbx, rcx
0x1400091d8  jnz     loc_140009273
0x1400091de  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1400091e3  jnz     loc_140009273
0x1400091e9  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1400091ee  jz      short loc_140009211
0x1400091f0  call    ?PathIsVolumeGUIDWorker@@YAHPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x1400091f5  mov     ecx, eax
0x1400091f7  neg     eax
0x1400091f9  sbb     rdx, rdx
0x1400091fc  xor     r8d, r8d
0x1400091ff  not     rdx
0x140009202  and     edx, 2
0x140009205  test    ecx, ecx
0x140009207  setz    r8b
0x14000920b  test    ecx, ecx
0x14000920d  jnz     short loc_140009273
0x14000920f  jmp     short loc_140009267
0x140009211  mov     esi, 5
0x140009216  lea     r10, aUnc; "\\UNC\\"
0x14000921d  lea     r11, [rcx+6]
0x140009221  movzx   ecx, word ptr [r11]
0x140009225  lea     eax, [rcx-41h]
0x140009228  cmp     eax, 19h
0x14000922b  lea     edx, [rcx+20h]
0x14000922e  cmova   edx, ecx
0x140009231  movzx   ecx, word ptr [r10]
0x140009235  lea     eax, [rcx-41h]
0x140009238  cmp     eax, 19h
0x14000923b  lea     r9d, [rcx+20h]
0x14000923f  cmova   r9d, ecx
0x140009243  sub     esi, 1
0x140009246  jz      short loc_140009259
0x140009248  test    edx, edx
0x14000924a  jz      short loc_140009259
0x14000924c  add     r11, 2
0x140009250  add     r10, 2
0x140009254  cmp     edx, r9d
0x140009257  jz      short loc_140009221
0x140009259  cmp     edx, r9d
0x14000925c  jnz     short loc_140009273
0x14000925e  mov     edx, 8
0x140009263  lea     r8d, [rdx-7]
0x140009267  test    rdi, rdi
0x14000926a  jz      short loc_140009273
0x14000926c  lea     rcx, [rbx+rdx*2]
0x140009270  mov     [rdi], rcx
0x140009273  mov     rbx, [rsp+28h+arg_0]
0x140009278  mov     eax, r8d
0x14000927b  mov     rsi, [rsp+28h+arg_8]
0x140009280  add     rsp, 20h
0x140009284  pop     rdi
0x140009285  retn
```
