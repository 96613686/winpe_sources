# UIBase::ThemedImageResource::Update(void)

- ea: `0x180005f70`
- end: `0x1800060a6`
- name: `?Update@ThemedImageResource@UIBase@@QEAA_NXZ`
- size: `310`
- prototype: `bool __fastcall(UIBase::ThemedImageResource *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004fe0`
- `0x180005f04`

## callees

- `0x180005f70`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180005fbd`
- `USER32!SystemParametersInfoW` at `0x180005fbd`
- `USER32!GetSysColor` at `0x180005fd9`
- `USER32!GetSysColor` at `0x180005fe6`
- `USER32!GetSysColor` at `0x180005fd9`
- `USER32!GetSysColor` at `0x180005fe6`

## pseudocode

```c
char __fastcall UIBase::ThemedImageResource::Update(UIBase::ThemedImageResource *this)
{
  int v1; // eax
  char v3; // bl
  DWORD SysColor; // edi
  DWORD v5; // eax
  char v6; // cl
  _BYTE *v7; // rax
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_DWORD *)this;
  if ( !*(_DWORD *)this || v1 == *((_DWORD *)this + 1) && v1 == *((_DWORD *)this + 2) )
    return 0;
  pvParam = 0;
  LODWORD(pvParam) = 16;
  v3 = SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) && (BYTE4(pvParam) & 1) != 0;
  SysColor = GetSysColor(5);
  v5 = GetSysColor(8);
  v6 = (unsigned __int8)((299 * (unsigned __int8)v5 + 114 * BYTE2(v5) + 587 * BYTE1(v5)) / 0x3E8u) < (unsigned __int8)((299 * (unsigned __int8)SysColor + 114 * BYTE2(SysColor) + 587 * BYTE1(SysColor)) / 0x3E8u);
  v7 = (char *)this + 13;
  if ( v3 == *((_BYTE *)this + 12) && v6 == *v7 )
  {
    *((_BYTE *)this + 12) = v3;
    *v7 = v6;
    return 0;
  }
  else
  {
    *((_BYTE *)this + 12) = v3;
    *v7 = v6;
    return 1;
  }
}

```

## disassembly

```asm
0x180005f70  push    rsi
0x180005f72  sub     rsp, 30h
0x180005f76  mov     eax, [rcx]
0x180005f78  mov     rsi, rcx
0x180005f7b  test    eax, eax
0x180005f7d  jz      loc_18000609E
0x180005f83  cmp     eax, [rcx+4]
0x180005f86  jnz     short loc_180005F91
0x180005f88  cmp     eax, [rcx+8]
0x180005f8b  jz      loc_18000609E
0x180005f91  xorps   xmm0, xmm0
0x180005f94  mov     [rsp+38h+arg_0], rbx
0x180005f99  movups  [rsp+38h+pvParam], xmm0
0x180005f9e  xor     r9d, r9d; fWinIni
0x180005fa1  mov     dword ptr [rsp+38h+pvParam], 10h
0x180005fa9  lea     r8, [rsp+38h+pvParam]; pvParam
0x180005fae  mov     [rsp+38h+arg_8], rdi
0x180005fb3  mov     edx, 10h; uiParam
0x180005fb8  mov     ecx, 42h ; 'B'; uiAction
0x180005fbd  call    cs:__imp_SystemParametersInfoW
0x180005fc3  test    eax, eax
0x180005fc5  jz      short loc_180005FD2
0x180005fc7  test    byte ptr [rsp+38h+pvParam+4], 1
0x180005fcc  jz      short loc_180005FD2
0x180005fce  mov     bl, 1
0x180005fd0  jmp     short loc_180005FD4
0x180005fd2  xor     bl, bl
0x180005fd4  mov     ecx, 5; nIndex
0x180005fd9  call    cs:__imp_GetSysColor
0x180005fdf  mov     ecx, 8; nIndex
0x180005fe4  mov     edi, eax
0x180005fe6  call    cs:__imp_GetSysColor
0x180005fec  movzx   ecx, ax
0x180005fef  shr     ecx, 8
0x180005ff2  imul    r8d, ecx, 24Bh
0x180005ff9  mov     ecx, eax
0x180005ffb  shr     ecx, 10h
0x180005ffe  movzx   ecx, cl
0x180006001  imul    edx, ecx, 72h ; 'r'
0x180006004  movzx   ecx, al
0x180006007  mov     eax, 10624DD3h
0x18000600c  add     r8d, edx
0x18000600f  imul    edx, ecx, 12Bh
0x180006015  movzx   ecx, di
0x180006018  shr     ecx, 8
0x18000601b  imul    r9d, ecx, 24Bh
0x180006022  mov     ecx, edi
0x180006024  shr     ecx, 10h
0x180006027  add     r8d, edx
0x18000602a  movzx   ecx, cl
0x18000602d  mul     r8d
0x180006030  imul    r8d, ecx, 72h ; 'r'
0x180006034  movzx   ecx, dil
0x180006038  mov     eax, 10624DD3h
0x18000603d  mov     rdi, [rsp+38h+arg_8]
0x180006042  mov     r10d, edx
0x180006045  shr     r10d, 6
0x180006049  add     r9d, r8d
0x18000604c  imul    r8d, ecx, 12Bh
0x180006053  add     r9d, r8d
0x180006056  mul     r9d
0x180006059  shr     edx, 6
0x18000605c  cmp     r10b, dl
0x18000605f  jnb     short loc_180006065
0x180006061  mov     cl, 1
0x180006063  jmp     short loc_180006067
0x180006065  xor     cl, cl
0x180006067  lea     rax, [rsi+0Dh]
0x18000606b  cmp     bl, [rsi+0Ch]
0x18000606e  jnz     short loc_180006089
0x180006070  cmp     cl, [rax]
0x180006072  jnz     short loc_180006089
0x180006074  xor     dl, dl
0x180006076  mov     [rsi+0Ch], bl
0x180006079  mov     rbx, [rsp+38h+arg_0]
0x18000607e  mov     [rax], cl
0x180006080  movzx   eax, dl
0x180006083  add     rsp, 30h
0x180006087  pop     rsi
0x180006088  retn
0x180006089  mov     dl, 1
0x18000608b  mov     [rsi+0Ch], bl
0x18000608e  mov     rbx, [rsp+38h+arg_0]
0x180006093  mov     [rax], cl
0x180006095  movzx   eax, dl
0x180006098  add     rsp, 30h
0x18000609c  pop     rsi
0x18000609d  retn
0x18000609e  xor     al, al
0x1800060a0  add     rsp, 30h
0x1800060a4  pop     rsi
0x1800060a5  retn
```
