# ShieldProvider::ShieldUtilRegOpenKey(HKEY__ * *,ushort const *,ulong)

- ea: `0x140007384`
- end: `0x140007429`
- name: `?ShieldUtilRegOpenKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z`
- size: `165`
- prototype: `__int64 __fastcall(ShieldProvider *this, HKEY *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140002c18`
- `0x140003e58`
- `0x140004588`
- `0x140005110`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140007248`
- `0x140007384`
- `0x14000fe34`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldUtilRegOpenKey(
        ShieldProvider *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // edi
  HKEY *v6; // rdx
  int PersistedKey; // ebx
  HKEY v9; // rbx
  unsigned __int64 v10; // rdx
  unsigned int v11; // edi
  unsigned int v12; // [rsp+20h] [rbp-8h]
  HKEY v13; // [rsp+48h] [rbp+20h] BYREF

  v4 = (unsigned int)a3;
  v13 = 0;
  PersistedKey = ShieldProvider::GetPersistedKey(this, (const unsigned __int16 *)a2, (const unsigned __int16 *)&v13, a4);
  if ( PersistedKey >= 0 )
  {
    v9 = v13;
    v11 = CommonUtil::UtilRegOpenKey(this, v6, v13, (const unsigned __int16 *)v4, v12);
    if ( v9 )
      operator delete(v9, v10);
    return v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
        (unsigned int)PersistedKey);
    if ( v13 )
      operator delete(v13, (unsigned __int64)v6);
    return (unsigned int)PersistedKey;
  }
}

```

## disassembly

```asm
0x140007384  mov     rax, rsp
0x140007387  mov     [rax+8], rbx
0x14000738b  mov     [rax+10h], rsi
0x14000738f  push    rdi; unsigned int
0x140007390  sub     rsp, 20h
0x140007394  mov     edi, r8d
0x140007397  mov     qword ptr [rax+20h], 0
0x14000739f  lea     r8, [rax+20h]; unsigned __int16 *
0x1400073a3  mov     rsi, rcx
0x1400073a6  call    ?GetPersistedKey@ShieldProvider@@YAJPEBG0PEAPEAG@Z; ShieldProvider::GetPersistedKey(ushort const *,ushort const *,ushort * *)
0x1400073ab  mov     ebx, eax
0x1400073ad  test    eax, eax
0x1400073af  jns     short loc_1400073F5
0x1400073b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073b8  lea     rax, WPP_GLOBAL_Control
0x1400073bf  cmp     rcx, rax
0x1400073c2  jz      short loc_1400073E2
0x1400073c4  test    byte ptr [rcx+1Ch], 1
0x1400073c8  jz      short loc_1400073E2
0x1400073ca  mov     rcx, [rcx+10h]
0x1400073ce  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1400073d5  mov     edx, 1Ch
0x1400073da  mov     r9d, ebx
0x1400073dd  call    WPP_SF_d
0x1400073e2  mov     rcx, [rsp+28h+arg_18]; void *
0x1400073e7  test    rcx, rcx
0x1400073ea  jz      short loc_1400073F1
0x1400073ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400073f1  mov     eax, ebx
0x1400073f3  jmp     short loc_140007419
0x1400073f5  mov     rbx, [rsp+28h+arg_18]
0x1400073fa  mov     r9d, edi; unsigned __int16 *
0x1400073fd  mov     r8, rbx; HKEY
0x140007400  mov     rcx, rsi; this
0x140007403  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x140007408  mov     edi, eax
0x14000740a  test    rbx, rbx
0x14000740d  jz      short loc_140007417
0x14000740f  mov     rcx, rbx; void *
0x140007412  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007417  mov     eax, edi
0x140007419  mov     rbx, [rsp+28h+arg_0]
0x14000741e  mov     rsi, [rsp+28h+arg_8]
0x140007423  add     rsp, 20h
0x140007427  pop     rdi
0x140007428  retn
```
