# RPC_UUID::ConvertToString(ushort *)

- ea: `0x1800046d8`
- end: `0x1800048ab`
- name: `?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z`
- size: `467`
- prototype: `unsigned __int16 *(RPC_UUID *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a1c`
- `0x180004678`

## callees

- `0x1800048b4`

## pseudocode

```c
unsigned __int16 *__fastcall RPC_UUID::ConvertToString(RPC_UUID *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rax
  __int64 v3; // r9
  unsigned int v4; // edx
  unsigned int v5; // ecx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *result; // rax

  v2 = ULongToHexString(a2, *(_DWORD *)this);
  *v2 = 45;
  v4 = *(unsigned __int16 *)(v3 + 4);
  v2[1] = HexDigits[(unsigned __int64)*(unsigned __int16 *)(v3 + 4) >> 12];
  v2[2] = HexDigits[((unsigned __int64)v4 >> 8) & 0xF];
  v2[3] = HexDigits[((unsigned __int64)v4 >> 4) & 0xF];
  v2[4] = HexDigits[v4 & 0xF];
  v2[5] = 45;
  v5 = *(unsigned __int16 *)(v3 + 6);
  v2[6] = HexDigits[(unsigned __int64)*(unsigned __int16 *)(v3 + 6) >> 12];
  v2[7] = HexDigits[((unsigned __int64)v5 >> 8) & 0xF];
  v2[8] = HexDigits[((unsigned __int64)v5 >> 4) & 0xF];
  v2[9] = HexDigits[v5 & 0xF];
  v2[10] = 45;
  v6 = *(_BYTE *)(v3 + 8) & 0xF;
  v2[11] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 8) >> 4];
  v2[12] = HexDigits[v6];
  v7 = *(_BYTE *)(v3 + 9) & 0xF;
  v2[13] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 9) >> 4];
  v2[14] = HexDigits[v7];
  v2[15] = 45;
  v8 = *(_BYTE *)(v3 + 10) & 0xF;
  v2[16] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 10) >> 4];
  v2[17] = HexDigits[v8];
  v9 = *(_BYTE *)(v3 + 11) & 0xF;
  v2[18] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 11) >> 4];
  v2[19] = HexDigits[v9];
  v10 = *(_BYTE *)(v3 + 12) & 0xF;
  v2[20] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 12) >> 4];
  v2[21] = HexDigits[v10];
  v11 = *(_BYTE *)(v3 + 13) & 0xF;
  v2[22] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 13) >> 4];
  v2[23] = HexDigits[v11];
  v12 = *(_BYTE *)(v3 + 14) & 0xF;
  v2[24] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 14) >> 4];
  v2[25] = HexDigits[v12];
  v13 = *(_BYTE *)(v3 + 15) & 0xF;
  v2[26] = HexDigits[(unsigned __int64)*(unsigned __int8 *)(v3 + 15) >> 4];
  v2[27] = HexDigits[v13];
  result = v2 + 28;
  *result = 0;
  return result;
}

```

## disassembly

```asm
0x1800046d8  push    rbx
0x1800046da  sub     rsp, 20h
0x1800046de  mov     rax, rdx
0x1800046e1  mov     r9, rcx
0x1800046e4  mov     edx, [rcx]; unsigned int
0x1800046e6  mov     rcx, rax; unsigned __int16 *
0x1800046e9  call    ?ULongToHexString@@YAPEAGPEAGK@Z; ULongToHexString(ushort *,ulong)
0x1800046ee  lea     rbx, ?HexDigits@@3QBGB; "0123456789abcdef"
0x1800046f5  mov     r10d, 2Dh ; '-'
0x1800046fb  mov     [rax], r10w
0x1800046ff  lea     r8, [rax+4]
0x180004703  movzx   edx, word ptr [r9+4]
0x180004708  lea     r11d, [r10-1Eh]
0x18000470c  mov     ecx, edx
0x18000470e  shr     rcx, 0Ch
0x180004712  movzx   ecx, word ptr [rbx+rcx*2]
0x180004716  mov     [rax+2], cx
0x18000471a  mov     eax, edx
0x18000471c  shr     rax, 8
0x180004720  and     rax, r11
0x180004723  movzx   eax, word ptr [rbx+rax*2]
0x180004727  mov     [r8], ax
0x18000472b  mov     eax, edx
0x18000472d  shr     rax, 4
0x180004731  and     rdx, r11
0x180004734  and     rax, r11
0x180004737  movzx   eax, word ptr [rbx+rax*2]
0x18000473b  mov     [r8+2], ax
0x180004740  movzx   eax, word ptr [rbx+rdx*2]
0x180004744  mov     [r8+4], ax
0x180004749  mov     [r8+6], r10w
0x18000474e  movzx   ecx, word ptr [r9+6]
0x180004753  mov     eax, ecx
0x180004755  shr     rax, 0Ch
0x180004759  movzx   eax, word ptr [rbx+rax*2]
0x18000475d  mov     [r8+8], ax
0x180004762  mov     eax, ecx
0x180004764  shr     rax, 8
0x180004768  and     rax, r11
0x18000476b  movzx   eax, word ptr [rbx+rax*2]
0x18000476f  mov     [r8+0Ah], ax
0x180004774  mov     eax, ecx
0x180004776  shr     rax, 4
0x18000477a  and     rcx, r11
0x18000477d  and     rax, r11
0x180004780  movzx   eax, word ptr [rbx+rax*2]
0x180004784  mov     [r8+0Ch], ax
0x180004789  movzx   eax, word ptr [rbx+rcx*2]
0x18000478d  mov     [r8+0Eh], ax
0x180004792  mov     [r8+10h], r10w
0x180004797  movzx   ecx, byte ptr [r9+8]
0x18000479c  mov     eax, ecx
0x18000479e  and     rcx, r11
0x1800047a1  shr     rax, 4
0x1800047a5  movzx   eax, word ptr [rbx+rax*2]
0x1800047a9  mov     [r8+12h], ax
0x1800047ae  movzx   eax, word ptr [rbx+rcx*2]
0x1800047b2  mov     [r8+14h], ax
0x1800047b7  movzx   ecx, byte ptr [r9+9]
0x1800047bc  mov     eax, ecx
0x1800047be  and     rcx, r11
0x1800047c1  shr     rax, 4
0x1800047c5  movzx   eax, word ptr [rbx+rax*2]
0x1800047c9  mov     [r8+16h], ax
0x1800047ce  movzx   eax, word ptr [rbx+rcx*2]
0x1800047d2  mov     [r8+18h], ax
0x1800047d7  mov     [r8+1Ah], r10w
0x1800047dc  movzx   ecx, byte ptr [r9+0Ah]
0x1800047e1  mov     eax, ecx
0x1800047e3  and     rcx, r11
0x1800047e6  shr     rax, 4
0x1800047ea  movzx   eax, word ptr [rbx+rax*2]
0x1800047ee  mov     [r8+1Ch], ax
0x1800047f3  movzx   eax, word ptr [rbx+rcx*2]
0x1800047f7  mov     [r8+1Eh], ax
0x1800047fc  movzx   ecx, byte ptr [r9+0Bh]
0x180004801  mov     eax, ecx
0x180004803  shr     rax, 4
0x180004807  and     rcx, r11
0x18000480a  movzx   eax, word ptr [rbx+rax*2]
0x18000480e  mov     [r8+20h], ax
0x180004813  movzx   eax, word ptr [rbx+rcx*2]
0x180004817  mov     [r8+22h], ax
0x18000481c  movzx   ecx, byte ptr [r9+0Ch]
0x180004821  mov     eax, ecx
0x180004823  and     rcx, r11
0x180004826  shr     rax, 4
0x18000482a  movzx   eax, word ptr [rbx+rax*2]
0x18000482e  mov     [r8+24h], ax
0x180004833  movzx   eax, word ptr [rbx+rcx*2]
0x180004837  mov     [r8+26h], ax
0x18000483c  movzx   ecx, byte ptr [r9+0Dh]
0x180004841  mov     eax, ecx
0x180004843  and     rcx, r11
0x180004846  shr     rax, 4
0x18000484a  movzx   eax, word ptr [rbx+rax*2]
0x18000484e  mov     [r8+28h], ax
0x180004853  movzx   eax, word ptr [rbx+rcx*2]
0x180004857  mov     [r8+2Ah], ax
0x18000485c  movzx   ecx, byte ptr [r9+0Eh]
0x180004861  mov     eax, ecx
0x180004863  and     rcx, r11
0x180004866  shr     rax, 4
0x18000486a  movzx   eax, word ptr [rbx+rax*2]
0x18000486e  mov     [r8+2Ch], ax
0x180004873  movzx   eax, word ptr [rbx+rcx*2]
0x180004877  mov     [r8+2Eh], ax
0x18000487c  movzx   ecx, byte ptr [r9+0Fh]
0x180004881  mov     eax, ecx
0x180004883  and     rcx, r11
0x180004886  shr     rax, 4
0x18000488a  movzx   eax, word ptr [rbx+rax*2]
0x18000488e  mov     [r8+30h], ax
0x180004893  movzx   eax, word ptr [rbx+rcx*2]
0x180004897  xor     ecx, ecx
0x180004899  mov     [r8+32h], ax
0x18000489e  lea     rax, [r8+34h]
0x1800048a2  mov     [rax], cx
0x1800048a5  add     rsp, 20h
0x1800048a9  pop     rbx
0x1800048aa  retn
```
