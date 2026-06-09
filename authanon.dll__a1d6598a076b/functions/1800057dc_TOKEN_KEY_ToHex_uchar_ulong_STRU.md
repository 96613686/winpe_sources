# TOKEN_KEY::ToHex(uchar *,ulong,STRU *)

- ea: `0x1800057dc`
- end: `0x18000587b`
- name: `?ToHex@TOKEN_KEY@@SAJPEAEKPEAVSTRU@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fa8`

## callees

- `0x1800057dc`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005806`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005806`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000586a`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000586a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800057f7`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800057f7`

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::ToHex(unsigned __int8 *a1, unsigned int a2, struct STRU *a3)
{
  int v6; // edi
  unsigned __int16 *Str; // rax
  __int64 v8; // r9
  __int64 i; // r10
  __int64 v10; // r9
  unsigned int v11; // ecx

  v6 = STRU::Resize(a3, 4 * a2 + 2);
  if ( v6 >= 0 )
  {
    Str = STRU::QueryStr(a3);
    v8 = 0;
    for ( i = 0; (unsigned int)i < a2; v8 = (unsigned int)(v10 + 1) )
    {
      Str[v8] = (a1[i] >> 4) + 87 + (a1[i] >> 4 < 0xAu ? 0xFFD9 : 0);
      v10 = (unsigned int)(v8 + 1);
      v11 = a1[i] & 0xF;
      i = (unsigned int)(i + 1);
      Str[v10] = v11 + (v11 < 0xA ? 48 : 87);
    }
    STRU::SetLen(a3, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800057dc  push    rbx
0x1800057de  push    rbp
0x1800057df  push    rsi
0x1800057e0  push    rdi
0x1800057e1  sub     rsp, 28h
0x1800057e5  mov     esi, edx
0x1800057e7  mov     rbp, rcx
0x1800057ea  lea     edx, ds:2[rdx*4]
0x1800057f1  mov     rcx, r8
0x1800057f4  mov     rbx, r8
0x1800057f7  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800057fd  mov     edi, eax
0x1800057ff  test    eax, eax
0x180005801  js      short loc_180005870
0x180005803  mov     rcx, rbx
0x180005806  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000580c  xor     r9d, r9d
0x18000580f  xor     r10d, r10d
0x180005812  mov     r11, rax
0x180005815  test    esi, esi
0x180005817  jz      short loc_180005864
0x180005819  movzx   eax, byte ptr [r10+rbp]
0x18000581e  shr     eax, 4
0x180005821  cmp     eax, 0Ah
0x180005824  sbb     cx, cx
0x180005827  add     ax, 57h ; 'W'
0x18000582b  and     cx, 0FFD9h
0x180005830  add     cx, ax
0x180005833  mov     [r11+r9*2], cx
0x180005838  inc     r9d
0x18000583b  movzx   ecx, byte ptr [r10+rbp]
0x180005840  and     ecx, 0Fh
0x180005843  cmp     ecx, 0Ah
0x180005846  sbb     ax, ax
0x180005849  inc     r10d
0x18000584c  and     ax, 0FFD9h
0x180005850  add     ax, 57h ; 'W'
0x180005854  add     ax, cx
0x180005857  mov     [r11+r9*2], ax
0x18000585c  inc     r9d
0x18000585f  cmp     r10d, esi
0x180005862  jb      short loc_180005819
0x180005864  mov     edx, r9d
0x180005867  mov     rcx, rbx
0x18000586a  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180005870  mov     eax, edi
0x180005872  add     rsp, 28h
0x180005876  pop     rdi
0x180005877  pop     rsi
0x180005878  pop     rbp
0x180005879  pop     rbx
0x18000587a  retn
```
