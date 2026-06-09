# CSingleSideReducer::EndFigure(bool)

- ea: `0x100437c10`
- end: `0x100437d1a`
- name: `?EndFigure@CSingleSideReducer@@UEAAJ_N@Z`
- size: `266`
- prototype: `__int64 __fastcall(CSingleSideReducer *__hidden this, bool)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100437c10`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::EndFigure(CSingleSideReducer *this, unsigned __int8 a2)
{
  __int64 result; // rax
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  bool v11; // zf
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // et2
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rcx

  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 56LL))((char *)this + 48);
  if ( (int)result < 0 )
  {
LABEL_12:
    _mm_lfence();
    return result;
  }
  if ( !*((_BYTE *)this + 104) )
  {
    if ( !*((_BYTE *)this + 106) )
    {
      _mm_lfence();
      v5 = *((_QWORD *)this + 5);
      *((_BYTE *)this + 105) = 1;
      return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 56LL))(v5, a2);
    }
    goto LABEL_12;
  }
  _mm_lfence();
  v6 = 0;
  if ( *((_DWORD *)this + 33) )
  {
    _mm_lfence();
    v6 = *((_DWORD *)this + 33) - 1;
  }
  v7 = *((_DWORD *)this + 37);
  v8 = (v6 * v7 + *((_DWORD *)this + 36) - 1) % v7;
  v9 = *(_QWORD *)(*((_QWORD *)this + 17) + 8LL * ((v6 * v7 + *((_DWORD *)this + 36) - 1) / v7));
  v10 = *(_DWORD *)(v9 + 72LL * (unsigned int)v8 + 20);
  v11 = v10 == 0;
  v12 = v10 - 1;
  v13 = *(_DWORD *)(v9 + 72LL * (unsigned int)v8 + 32);
  if ( v11 )
    v12 = 0;
  v14 = (unsigned int)(*(_DWORD *)(v9 + 72 * v8 + 36) * v12 - 1 + v13) % *(_DWORD *)(v9 + 72 * v8 + 36);
  v15 = (unsigned int)(*(_DWORD *)(v9 + 72 * v8 + 36) * v12 - 1 + v13) / *(_DWORD *)(v9 + 72 * v8 + 36);
  v16 = 1;
  v17 = v14;
  if ( *((double *)this + 8) < 0.0 )
    v16 = -1;
  *(_BYTE *)(56 * v17 + *(_QWORD *)(*(_QWORD *)(v9 + 72 * v8 + 24) + 8 * v15)) = v16 > 0;
  return 0;
}

```

## disassembly

```asm
0x100437c10  mov     [rsp+arg_0], rbx
0x100437c15  push    rdi
0x100437c16  sub     rsp, 20h
0x100437c1a  mov     rax, [rcx+30h]
0x100437c1e  mov     rbx, rcx
0x100437c21  add     rcx, 30h ; '0'
0x100437c25  movzx   edi, dl
0x100437c28  call    qword ptr [rax+38h]
0x100437c2b  test    eax, eax
0x100437c2d  js      loc_100437D0C
0x100437c33  cmp     byte ptr [rbx+68h], 0
0x100437c37  jnz     short loc_100437C63
0x100437c39  cmp     byte ptr [rbx+6Ah], 0
0x100437c3d  jnz     loc_100437D0C
0x100437c43  lfence
0x100437c46  mov     rcx, [rbx+28h]
0x100437c4a  movzx   edx, dil
0x100437c4e  mov     byte ptr [rbx+69h], 1
0x100437c52  mov     rax, [rcx]
0x100437c55  mov     rbx, [rsp+28h+arg_0]
0x100437c5a  add     rsp, 20h
0x100437c5e  pop     rdi
0x100437c5f  jmp     qword ptr [rax+38h]
0x100437c63  lfence
0x100437c66  xor     r11d, r11d
0x100437c69  mov     eax, r11d
0x100437c6c  cmp     [rbx+84h], eax
0x100437c72  jbe     short loc_100437C7F
0x100437c74  lfence
0x100437c77  mov     eax, [rbx+84h]
0x100437c7d  dec     eax
0x100437c7f  mov     r8d, [rbx+94h]
0x100437c86  xor     edx, edx
0x100437c88  mov     ecx, r8d
0x100437c8b  xorps   xmm0, xmm0
0x100437c8e  imul    ecx, eax
0x100437c91  mov     eax, [rbx+90h]
0x100437c97  dec     eax
0x100437c99  add     eax, ecx
0x100437c9b  div     r8d
0x100437c9e  mov     ecx, eax
0x100437ca0  mov     rax, [rbx+88h]
0x100437ca7  lea     r10, [rdx+rdx*8]
0x100437cab  mov     r9, [rax+rcx*8]
0x100437caf  mov     eax, [r9+r10*8+14h]
0x100437cb4  test    eax, eax
0x100437cb6  lea     ecx, [rax-1]
0x100437cb9  mov     eax, [r9+r10*8+20h]
0x100437cbe  cmovz   ecx, r11d
0x100437cc2  xor     edx, edx
0x100437cc4  imul    ecx, [r9+r10*8+24h]
0x100437cca  dec     ecx
0x100437ccc  add     eax, ecx
0x100437cce  div     dword ptr [r9+r10*8+24h]
0x100437cd3  comisd  xmm0, qword ptr [rbx+40h]
0x100437cd8  mov     r8d, eax
0x100437cdb  mov     eax, 1
0x100437ce0  mov     ecx, edx
0x100437ce2  mov     edx, 0FFFFFFFFh
0x100437ce7  cmova   eax, edx
0x100437cea  test    eax, eax
0x100437cec  mov     rax, [r9+r10*8+18h]
0x100437cf1  setnle  dl
0x100437cf4  imul    rcx, 38h ; '8'
0x100437cf8  mov     rax, [rax+r8*8]
0x100437cfc  mov     [rcx+rax], dl
0x100437cff  xor     eax, eax
0x100437d01  mov     rbx, [rsp+28h+arg_0]
0x100437d06  add     rsp, 20h
0x100437d0a  pop     rdi
0x100437d0b  retn
0x100437d0c  lfence
0x100437d0f  mov     rbx, [rsp+28h+arg_0]
0x100437d14  add     rsp, 20h
0x100437d18  pop     rdi
0x100437d19  retn
```
