# mbbcx_p::ParseTlvNSSAI(_MBB_TLV_IE * const,_WWAN_SINGLE_NSSAI *,ulong)

- ea: `0x140047814`
- end: `0x1400478dd`
- name: `?ParseTlvNSSAI@mbbcx_p@@YAXQEAU_MBB_TLV_IE@@PEAU_WWAN_SINGLE_NSSAI@@K@Z`
- size: `201`
- prototype: `void __fastcall(mbbcx_p *this, struct _MBB_TLV_IE *const, struct _WWAN_SINGLE_NSSAI *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140030100`
- `0x140034b50`
- `0x14003bf28`
- `0x14003c670`
- `0x14003cdf8`
- `0x14004041c`

## callees

- `0x140047814`

## pseudocode

```c
void __fastcall mbbcx_p::ParseTlvNSSAI(mbbcx_p *this, struct _MBB_TLV_IE *const a2, struct _WWAN_SINGLE_NSSAI *a3)
{
  unsigned int v4; // r11d
  unsigned __int8 *v5; // r10
  __int64 v6; // rbx
  unsigned __int8 *v7; // rcx
  __int64 v8; // rdx
  __int16 v9; // ax
  unsigned __int8 v10; // al

  if ( *((_DWORD *)this + 1) )
  {
    v4 = 0;
    v5 = (unsigned __int8 *)this + 8;
    if ( (_DWORD)a3 )
    {
      v6 = 0;
      do
      {
        v7 = v5 + 2;
        v8 = 2 * v6;
        *((_DWORD *)a2 + 2 * v8 + 2) = 0xFFFFFF;
        *((_WORD *)a2 + 4 * v8 + 3) = 0;
        *((_DWORD *)a2 + 2 * v8 + 3) = 0xFFFFFF;
        *((_DWORD *)a2 + 2 * v8) = 1;
        *((_WORD *)a2 + 4 * v8 + 2) = v5[1];
        if ( *v5 >= 4u )
        {
          *((_WORD *)a2 + 8 * v6 + 4) = *(_WORD *)v7;
          v7 = v5 + 5;
          *((_BYTE *)a2 + 16 * v6 + 10) = v5[4];
        }
        if ( *v5 == 2 || *v5 >= 5u )
        {
          *((_DWORD *)a2 + 4 * v6) = 3;
          v9 = *v7++;
          *((_WORD *)a2 + 8 * v6 + 3) = v9;
        }
        if ( *v5 == 8 )
        {
          *((_WORD *)a2 + 8 * v6 + 6) = *(_WORD *)v7;
          v10 = v7[2];
          v7 += 3;
          *((_BYTE *)a2 + 16 * v6 + 14) = v10;
        }
        ++v4;
        ++v6;
        v5 = v7;
      }
      while ( v4 < (unsigned int)a3 );
    }
  }
}

```

## disassembly

```asm
0x140047814  mov     [rsp+arg_0], rbx
0x140047819  cmp     dword ptr [rcx+4], 0
0x14004781d  mov     r9, rdx
0x140047820  jz      loc_1400478D6
0x140047826  xor     r11d, r11d
0x140047829  lea     r10, [rcx+8]
0x14004782d  test    r8d, r8d
0x140047830  jz      loc_1400478D6
0x140047836  xor     ebx, ebx
0x140047838  xor     eax, eax
0x14004783a  lea     rcx, [r10+2]
0x14004783e  mov     rdx, rbx
0x140047841  add     rdx, rdx
0x140047844  mov     dword ptr [r9+rdx*8+8], 0FFFFFFh
0x14004784d  mov     [r9+rdx*8+6], ax
0x140047853  mov     dword ptr [r9+rdx*8+0Ch], 0FFFFFFh
0x14004785c  mov     dword ptr [r9+rdx*8], 1
0x140047864  movzx   eax, byte ptr [r10+1]
0x140047869  mov     [r9+rdx*8+4], ax
0x14004786f  cmp     byte ptr [r10], 4
0x140047873  jb      short loc_14004788A
0x140047875  movzx   eax, word ptr [rcx]
0x140047878  mov     [r9+rdx*8+8], ax
0x14004787e  mov     al, [rcx+2]
0x140047881  add     rcx, 3
0x140047885  mov     [r9+rdx*8+0Ah], al
0x14004788a  mov     al, [r10]
0x14004788d  cmp     al, 2
0x14004788f  jz      short loc_140047895
0x140047891  cmp     al, 5
0x140047893  jb      short loc_1400478A9
0x140047895  mov     dword ptr [r9+rdx*8], 3
0x14004789d  movzx   eax, byte ptr [rcx]
0x1400478a0  inc     rcx
0x1400478a3  mov     [r9+rdx*8+6], ax
0x1400478a9  cmp     byte ptr [r10], 8
0x1400478ad  jnz     short loc_1400478C4
0x1400478af  movzx   eax, word ptr [rcx]
0x1400478b2  mov     [r9+rdx*8+0Ch], ax
0x1400478b8  mov     al, [rcx+2]
0x1400478bb  add     rcx, 3
0x1400478bf  mov     [r9+rdx*8+0Eh], al
0x1400478c4  inc     r11d
0x1400478c7  inc     rbx
0x1400478ca  mov     r10, rcx
0x1400478cd  cmp     r11d, r8d
0x1400478d0  jb      loc_140047838
0x1400478d6  mov     rbx, [rsp+arg_0]
0x1400478db  retn
```
