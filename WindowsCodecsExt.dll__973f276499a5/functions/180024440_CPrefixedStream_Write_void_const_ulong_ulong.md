# CPrefixedStream::Write(void const *,ulong,ulong *)

- ea: `0x180024440`
- end: `0x18002453b`
- name: `?Write@CPrefixedStream@@UEAAJPEBXKPEAK@Z`
- size: `251`
- prototype: `__int64 __fastcall(CPrefixedStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180012afc`
- `0x1800171c4`
- `0x180024440`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CPrefixedStream::Write(CPrefixedStream *this, const void *a2, __int64 a3, unsigned int *a4)
{
  HRESULT v6; // eax
  unsigned int v7; // r10d
  char *v8; // r11
  unsigned int v9; // ebx
  int v10; // ecx
  ULONG v11; // r8d
  unsigned int i; // esi
  char v13; // dl
  __int64 v14; // rcx
  unsigned int v15; // r10d
  __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  ULONG v19; // [rsp+50h] [rbp+8h] BYREF
  int v20; // [rsp+58h] [rbp+10h] BYREF

  v20 = 0;
  v19 = 0;
  v6 = ULongLongToULong(*((_QWORD *)this + 4), &v19);
  v9 = v6;
  if ( v6 < 0 )
    goto LABEL_2;
  if ( v8 )
  {
    v11 = v19;
    for ( i = 0; v11 < *((_DWORD *)this + 6) && i < v7; ++i )
    {
      v13 = *v8++;
      v14 = v11++;
      *(_BYTE *)(v14 + *((_QWORD *)this + 2)) = v13;
    }
    v15 = v7 - i;
    if ( i < v15 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)this + 1) + 32LL))(
             *((_QWORD *)this + 1),
             v8,
             v15,
             &v20);
      v9 = v6;
      if ( v6 < 0 )
      {
LABEL_2:
        if ( g_doStackCaptures )
        {
          v10 = v6;
LABEL_19:
          DoStackCapture(v10);
          return v9;
        }
        return v9;
      }
    }
    v16 = i + v20;
    if ( a4 )
      *a4 = v16;
    v17 = *((_QWORD *)this + 4) + v16;
    if ( v17 >= *((_QWORD *)this + 4) )
    {
      v9 = 0;
      *((_QWORD *)this + 4) = v17;
      return v9;
    }
    v9 = -2147024362;
    *((_QWORD *)this + 4) = -1;
  }
  else
  {
    v9 = -2147024809;
  }
  if ( g_doStackCaptures )
  {
    v10 = v9;
    goto LABEL_19;
  }
  return v9;
}

```

## disassembly

```asm
0x180024440  mov     rax, rsp
0x180024443  mov     [rax+18h], rbx
0x180024447  push    rsi
0x180024448  push    rdi
0x180024449  push    r14
0x18002444b  sub     rsp, 30h
0x18002444f  mov     r11, rdx
0x180024452  mov     dword ptr [rax+10h], 0
0x180024459  mov     rdi, rcx
0x18002445c  mov     dword ptr [rax+8], 0
0x180024463  mov     rcx, [rcx+20h]; ullOperand
0x180024467  lea     rdx, [rax+8]; pulResult
0x18002446b  mov     r14, r9
0x18002446e  mov     r10d, r8d
0x180024471  call    ULongLongToULong
0x180024476  mov     ebx, eax
0x180024478  test    eax, eax
0x18002447a  jns     short loc_180024490
0x18002447c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180024483  jz      loc_18002452B
0x180024489  mov     ecx, eax
0x18002448b  jmp     loc_180024526
0x180024490  test    r11, r11
0x180024493  jnz     short loc_18002449C
0x180024495  mov     ebx, 80070057h
0x18002449a  jmp     short loc_18002451B
0x18002449c  mov     r8d, [rsp+48h+arg_0]
0x1800244a1  xor     esi, esi
0x1800244a3  jmp     short loc_1800244BF
0x1800244a5  cmp     esi, r10d
0x1800244a8  jnb     short loc_1800244C5
0x1800244aa  mov     dl, [r11]
0x1800244ad  inc     r11
0x1800244b0  mov     rax, [rdi+10h]
0x1800244b4  mov     ecx, r8d
0x1800244b7  inc     r8d
0x1800244ba  inc     esi
0x1800244bc  mov     [rcx+rax], dl
0x1800244bf  cmp     r8d, [rdi+18h]
0x1800244c3  jb      short loc_1800244A5
0x1800244c5  sub     r10d, esi
0x1800244c8  cmp     esi, r10d
0x1800244cb  jnb     short loc_1800244EE
0x1800244cd  mov     rcx, [rdi+8]
0x1800244d1  lea     r9, [rsp+48h+arg_8]
0x1800244d6  mov     r8d, r10d
0x1800244d9  mov     rdx, r11
0x1800244dc  mov     rax, [rcx]
0x1800244df  mov     rax, [rax+20h]
0x1800244e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244e8  mov     ebx, eax
0x1800244ea  test    eax, eax
0x1800244ec  js      short loc_18002447C
0x1800244ee  mov     edx, [rsp+48h+arg_8]
0x1800244f2  add     edx, esi
0x1800244f4  test    r14, r14
0x1800244f7  jz      short loc_1800244FC
0x1800244f9  mov     [r14], edx
0x1800244fc  add     rdx, [rdi+20h]
0x180024500  cmp     rdx, [rdi+20h]
0x180024504  jb      short loc_18002450E
0x180024506  xor     ebx, ebx
0x180024508  mov     [rdi+20h], rdx
0x18002450c  jmp     short loc_18002452B
0x18002450e  mov     ebx, 80070216h
0x180024513  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18002451b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180024522  jz      short loc_18002452B
0x180024524  mov     ecx, ebx; int
0x180024526  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002452b  mov     eax, ebx
0x18002452d  mov     rbx, [rsp+48h+arg_10]
0x180024532  add     rsp, 30h
0x180024536  pop     r14
0x180024538  pop     rdi
0x180024539  pop     rsi
0x18002453a  retn
```
