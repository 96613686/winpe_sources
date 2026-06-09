# PathIsVolumeGUIDWorker(ushort const *)

- ea: `0x14000928c`
- end: `0x14000933e`
- name: `?PathIsVolumeGUIDWorker@@YAHPEBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009000`
- `0x1400091bc`

## callees

- `0x14000928c`

## pseudocode

```c
__int64 __fastcall PathIsVolumeGUIDWorker(const unsigned __int16 *a1)
{
  int v1; // edi
  const wchar_t *v2; // r10
  const unsigned __int16 *v4; // r11
  unsigned int v5; // r8d
  int v6; // edx
  int v7; // ecx
  int v8; // r9d
  int v9; // edx
  __int64 v10; // rdx
  unsigned __int16 v11; // cx

  v1 = 10;
  v2 = L"\\\\?\\Volume";
  v4 = a1;
  v5 = 1;
  do
  {
    v6 = *v4;
    v7 = *v2;
    v8 = v6 + 32;
    if ( (unsigned int)(v6 - 65) > 0x19 )
      v8 = *v4;
    v9 = v7 + 32;
    if ( (unsigned int)(v7 - 65) > 0x19 )
      v9 = *v2;
    if ( !--v1 )
      break;
    if ( !v8 )
      break;
    ++v4;
    ++v2;
  }
  while ( v8 == v9 );
  if ( v8 == v9 )
  {
    v10 = 0;
    while ( 1 )
    {
      v11 = a1[v10 + 10];
      if ( v11 != `StringIsGUIDWorker'::`2'::s_szGuid[v10]
        && (`StringIsGUIDWorker'::`2'::s_szGuid[v10] != 48
         || (unsigned __int16)(v11 - 48) > 9u && (unsigned __int16)(v11 - 65) > 5u && (unsigned __int16)(v11 - 97) > 5u) )
      {
        break;
      }
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= 0x26 )
        return v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000928c  mov     [rsp+arg_0], rbx
0x140009291  mov     [rsp+arg_8], rdi
0x140009296  mov     edi, 0Ah
0x14000929b  lea     r10, aVolume; "\\\\?\\Volume"
0x1400092a2  mov     rbx, rcx
0x1400092a5  mov     r11, rcx
0x1400092a8  lea     r8d, [rdi-9]
0x1400092ac  movzx   edx, word ptr [r11]
0x1400092b0  movzx   ecx, word ptr [r10]
0x1400092b4  lea     eax, [rdx-41h]
0x1400092b7  cmp     eax, 19h
0x1400092ba  lea     r9d, [rdx+20h]
0x1400092be  lea     eax, [rcx-41h]
0x1400092c1  cmova   r9d, edx
0x1400092c5  cmp     eax, 19h
0x1400092c8  lea     edx, [rcx+20h]
0x1400092cb  cmova   edx, ecx
0x1400092ce  sub     edi, r8d
0x1400092d1  jz      short loc_1400092E5
0x1400092d3  test    r9d, r9d
0x1400092d6  jz      short loc_1400092E5
0x1400092d8  add     r11, 2
0x1400092dc  add     r10, 2
0x1400092e0  cmp     r9d, edx
0x1400092e3  jz      short loc_1400092AC
0x1400092e5  cmp     r9d, edx
0x1400092e8  jnz     short loc_14000932D
0x1400092ea  xor     edx, edx
0x1400092ec  movzx   ecx, word ptr [rbx+rdx*2+14h]
0x1400092f1  lea     r9, ?s_szGuid@?1??StringIsGUIDWorker@@YAHPEBG@Z@4QBGB; "{00000000-0000-0000-0000-000000000000}"
0x1400092f8  cmp     cx, [r9+rdx*2]
0x1400092fd  jz      short loc_140009323
0x1400092ff  cmp     word ptr [r9+rdx*2], 30h ; '0'
0x140009305  jnz     short loc_14000932D
0x140009307  lea     eax, [rcx-30h]
0x14000930a  cmp     ax, 9
0x14000930e  jbe     short loc_140009323
0x140009310  lea     eax, [rcx-41h]
0x140009313  cmp     ax, 5
0x140009317  jbe     short loc_140009323
0x140009319  sub     cx, 61h ; 'a'
0x14000931d  cmp     cx, 5
0x140009321  ja      short loc_14000932D
0x140009323  add     edx, r8d
0x140009326  cmp     edx, 26h ; '&'
0x140009329  jb      short loc_1400092EC
0x14000932b  jmp     short loc_140009330
0x14000932d  xor     r8d, r8d
0x140009330  mov     rbx, [rsp+arg_0]
0x140009335  mov     eax, r8d
0x140009338  mov     rdi, [rsp+arg_8]
0x14000933d  retn
```
