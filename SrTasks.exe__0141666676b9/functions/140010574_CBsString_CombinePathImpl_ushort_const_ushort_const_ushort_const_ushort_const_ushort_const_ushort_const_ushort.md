# CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x140010574`
- end: `0x14001073c`
- name: `?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z`
- size: `456`
- prototype: `__int64 __fastcall(CBsString *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400039e4`
- `0x140006e40`

## callees

- `0x1400104ac`
- `0x140010574`
- `0x14001094e`
- `0x140010980`

## pseudocode

```c
__int64 __fastcall CBsString::_CombinePathImpl(
        CBsString *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  __int64 i; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r8d
  unsigned int v12; // edx
  __int64 v13; // r10
  BOOL v14; // r9d
  BOOL v15; // r11d
  unsigned __int16 *v16; // r8
  __int64 v17; // rax
  unsigned int v18; // ecx
  __int64 v19; // rax
  unsigned int j; // r9d
  __int64 v21; // rax
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+80h] [rbp-80h]
  _OWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-50h]
  unsigned int v30[20]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v31[20]; // [rsp+110h] [rbp+10h] BYREF

  v23[0] = a2;
  v23[1] = a3;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  memset(v28, 0, sizeof(v28));
  memset_0(v31, 0, sizeof(v31));
  memset_0(v30, 0, sizeof(v30));
  v22 = 92;
  if ( !a2 )
    return 2147942487LL;
  v7 = 0;
  for ( i = 0; i != 10; ++i )
  {
    v9 = v23[i];
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v9 + 2 * v10) );
    }
    else
    {
      LODWORD(v10) = 0;
    }
    *((_DWORD *)v28 + i) = v10;
  }
  v11 = *((_DWORD *)this + 2);
  v12 = 0;
  LODWORD(v13) = 0;
  v14 = 0;
  if ( v11 )
    LOBYTE(v14) = *(_WORD *)(*(_QWORD *)this + 2LL * (unsigned int)(v11 - 1)) == 92;
  v15 = v11 == 0;
  do
  {
    v16 = (unsigned __int16 *)v23[(unsigned int)v13];
    if ( v14 && *v16 == 92 )
    {
      ++v16;
      --*((_DWORD *)v28 + (unsigned int)v13);
    }
    else if ( !v15 && !v14 && *v16 != 92 )
    {
      v17 = v12++;
      v31[v17] = (unsigned __int16 *)&v22;
      v30[v17] = 1;
    }
    v18 = *((_DWORD *)v28 + (unsigned int)v13);
    v19 = v12++;
    v31[v19] = v16;
    v30[v19] = v18;
    v14 = v16[v18 - 1] == 92;
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= 0xA )
      break;
    v15 = 0;
  }
  while ( *((_DWORD *)v28 + v13) );
  for ( j = 0; j < v12; v7 += v30[v21] )
    v21 = j++;
  return CBsString::_Append(this, v12, v7, v30, (const unsigned __int16 **const)v31);
}

```

## disassembly

```asm
0x140010574  mov     [rsp-8+arg_8], rbx
0x140010579  mov     [rsp-8+arg_10], rsi
0x14001057e  push    rbp
0x14001057f  push    rdi
0x140010580  push    r14
0x140010582  lea     rbp, [rsp-0C0h]
0x14001058a  sub     rsp, 1C0h
0x140010591  mov     rax, cs:__security_cookie
0x140010598  xor     rax, rsp
0x14001059b  mov     [rbp+0D0h+var_20], rax
0x1400105a2  xorps   xmm0, xmm0
0x1400105a5  mov     [rsp+1D0h+var_190], rdx
0x1400105aa  xorps   xmm1, xmm1
0x1400105ad  mov     [rsp+1D0h+var_188], r8
0x1400105b2  mov     rbx, rdx
0x1400105b5  movdqa  [rsp+1D0h+var_180], xmm0
0x1400105bb  mov     rdi, rcx
0x1400105be  movdqa  [rsp+1D0h+var_170], xmm1
0x1400105c4  xor     eax, eax
0x1400105c6  movdqa  [rsp+1D0h+var_160], xmm0
0x1400105cc  xor     edx, edx; Val
0x1400105ce  movdqa  [rbp+0D0h+var_150], xmm1
0x1400105d3  mov     r8d, 0A0h; Size
0x1400105d9  mov     [rbp+0D0h+var_120], rax
0x1400105dd  lea     rcx, [rbp+0D0h+var_C0]; void *
0x1400105e1  movups  [rbp+0D0h+var_140], xmm0
0x1400105e5  movups  [rbp+0D0h+var_130], xmm0
0x1400105e9  call    memset_0
0x1400105ee  xor     edx, edx; Val
0x1400105f0  lea     rcx, [rbp+0D0h+var_110]; void *
0x1400105f4  lea     r8d, [rdx+50h]; Size
0x1400105f8  call    memset_0
0x1400105fd  xor     esi, esi
0x1400105ff  mov     r14d, 5Ch ; '\'
0x140010605  mov     [rsp+1D0h+var_1A0], r14d
0x14001060a  test    rbx, rbx
0x14001060d  jnz     short loc_140010619
0x14001060f  mov     eax, 80070057h
0x140010614  jmp     loc_140010715
0x140010619  mov     ebx, esi
0x14001061b  mov     rax, rsi
0x14001061e  mov     rdx, [rsp+rax*8+1D0h+var_190]
0x140010623  test    rdx, rdx
0x140010626  jnz     short loc_14001062C
0x140010628  mov     ecx, esi
0x14001062a  jmp     short loc_140010639
0x14001062c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140010630  inc     rcx
0x140010633  cmp     [rdx+rcx*2], si
0x140010637  jnz     short loc_140010630
0x140010639  mov     dword ptr [rbp+rax*4+0D0h+var_140], ecx
0x14001063d  inc     rax
0x140010640  cmp     rax, 0Ah
0x140010644  jnz     short loc_14001061E
0x140010646  mov     r8d, [rdi+8]
0x14001064a  mov     edx, esi
0x14001064c  mov     r10d, esi
0x14001064f  mov     r9d, esi
0x140010652  test    r8d, r8d
0x140010655  jz      short loc_140010667
0x140010657  mov     rax, [rdi]
0x14001065a  lea     ecx, [r8-1]
0x14001065e  cmp     [rax+rcx*2], r14w
0x140010663  setz    r9b
0x140010667  test    r8d, r8d
0x14001066a  mov     r11d, esi
0x14001066d  setz    r11b
0x140010671  mov     ecx, r10d
0x140010674  mov     r8, [rsp+rcx*8+1D0h+var_190]
0x140010679  test    r9d, r9d
0x14001067c  jz      short loc_14001068E
0x14001067e  cmp     [r8], r14w
0x140010682  jnz     short loc_14001068E
0x140010684  add     r8, 2
0x140010688  dec     dword ptr [rbp+rcx*4+0D0h+var_140]
0x14001068c  jmp     short loc_1400106B4
0x14001068e  test    r11d, r11d
0x140010691  jnz     short loc_1400106B4
0x140010693  test    r9d, r9d
0x140010696  jnz     short loc_1400106B4
0x140010698  cmp     [r8], r14w
0x14001069c  jz      short loc_1400106B4
0x14001069e  mov     eax, edx
0x1400106a0  lea     r9, [rsp+1D0h+var_1A0]
0x1400106a5  inc     edx
0x1400106a7  mov     [rbp+rax*8+0D0h+var_C0], r9
0x1400106ac  mov     [rbp+rax*4+0D0h+var_110], 1
0x1400106b4  mov     ecx, dword ptr [rbp+rcx*4+0D0h+var_140]
0x1400106b8  mov     r9d, esi
0x1400106bb  mov     eax, edx
0x1400106bd  inc     edx; unsigned int
0x1400106bf  mov     [rbp+rax*8+0D0h+var_C0], r8
0x1400106c4  mov     [rbp+rax*4+0D0h+var_110], ecx
0x1400106c8  lea     eax, [rcx-1]
0x1400106cb  cmp     [r8+rax*2], r14w
0x1400106d0  setz    r9b
0x1400106d4  inc     r10d
0x1400106d7  cmp     r10d, 0Ah
0x1400106db  jnb     short loc_1400106E7
0x1400106dd  mov     r11d, esi
0x1400106e0  cmp     dword ptr [rbp+r10*4+0D0h+var_140], esi
0x1400106e5  ja      short loc_140010671
0x1400106e7  mov     r9d, esi
0x1400106ea  test    edx, edx
0x1400106ec  jz      short loc_1400106FD
0x1400106ee  mov     eax, r9d
0x1400106f1  inc     r9d
0x1400106f4  add     ebx, [rbp+rax*4+0D0h+var_110]
0x1400106f8  cmp     r9d, edx
0x1400106fb  jb      short loc_1400106EE
0x1400106fd  lea     rax, [rbp+0D0h+var_C0]
0x140010701  mov     r8d, ebx; unsigned int
0x140010704  lea     r9, [rbp+0D0h+var_110]; unsigned int *
0x140010708  mov     [rsp+1D0h+var_1B0], rax; unsigned __int16 **
0x14001070d  mov     rcx, rdi; this
0x140010710  call    ?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z; CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)
0x140010715  mov     rcx, [rbp+0D0h+var_20]
0x14001071c  xor     rcx, rsp; StackCookie
0x14001071f  call    __security_check_cookie
0x140010724  lea     r11, [rsp+1D0h+var_10]
0x14001072c  mov     rbx, [r11+28h]
0x140010730  mov     rsi, [r11+30h]
0x140010734  mov     rsp, r11
0x140010737  pop     r14
0x140010739  pop     rdi
0x14001073a  pop     rbp
0x14001073b  retn
```
