# IsMcxDevice(ushort *,ulong)

- ea: `0x18000f49c`
- end: `0x18000f64a`
- name: `?IsMcxDevice@@YAHPEAGK@Z`
- size: `430`
- prototype: `__int64 __fastcall(wchar_t *Str, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000eadc`

## callees

- `0x18000a644`
- `0x18000a66c`
- `0x18000f49c`
- `0x180010fa0`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x18000f542`
- `msvcrt!_wcslwr_s` at `0x18000f542`
- `msvcrt!wcsstr` at `0x18000f55a`
- `msvcrt!wcsstr` at `0x18000f55a`

## string_xrefs

- `0x18000f550`: `urn:schemas-microsoft-com:device:MediaCenterExtender:`

## pseudocode

```c
__int64 __fastcall IsMcxDevice(wchar_t *Str, unsigned int a2, __int64 a3)
{
  unsigned __int64 v3; // r14
  _QWORD *v5; // r10
  unsigned int v6; // esi
  __int64 v7; // rbp
  __int64 v8; // rdi
  wchar_t *v9; // rax

  v3 = a2;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 0;
  if ( Str && (unsigned int)v3 >= 2 )
  {
    LODWORD(v7) = 0;
    while ( 1 )
    {
      if ( !*Str )
        goto LABEL_19;
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
        WPP_SF_S(v5[2], 49, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, Str);
      v8 = -1;
      do
        ++v8;
      while ( Str[v8] );
      if ( !_wcslwr_s(Str, v8 + 1) )
        break;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
LABEL_29:
        v5 = WPP_GLOBAL_Control;
      }
      if ( v8 + (unsigned __int64)(unsigned int)(v7 + 1) >= v3 )
        goto LABEL_19;
      v7 = (unsigned int)(v8 + v7 + 1);
      Str += v7;
    }
    v9 = wcsstr(Str, L"urn:schemas-microsoft-com:device:MediaCenterExtender:");
    if ( v9 && v9 == Str )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, Str);
        v5 = WPP_GLOBAL_Control;
      }
      v6 = 1;
      goto LABEL_19;
    }
    goto LABEL_29;
  }
LABEL_19:
  if ( v5 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v5 + 28) & 8) != 0 )
    {
      WPP_SF_l(v5[2], 52, a3, v6);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
      WPP_SF_(v5[2], 53, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f49c  push    rbx
0x18000f49e  push    rbp
0x18000f49f  push    rsi
0x18000f4a0  push    rdi
0x18000f4a1  push    r12
0x18000f4a3  push    r13
0x18000f4a5  push    r14
0x18000f4a7  push    r15
0x18000f4a9  sub     rsp, 28h
0x18000f4ad  mov     r14d, edx
0x18000f4b0  mov     rbx, rcx
0x18000f4b3  mov     r10, cs:WPP_GLOBAL_Control
0x18000f4ba  lea     r12, WPP_GLOBAL_Control
0x18000f4c1  lea     r13, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f4c8  cmp     r10, r12
0x18000f4cb  jz      short loc_18000F4EC
0x18000f4cd  test    byte ptr [r10+1Ch], 20h
0x18000f4d2  jz      short loc_18000F4EC
0x18000f4d4  mov     rcx, [r10+10h]
0x18000f4d8  mov     edx, 30h ; '0'
0x18000f4dd  mov     r8, r13
0x18000f4e0  call    WPP_SF_
0x18000f4e5  mov     r10, cs:WPP_GLOBAL_Control
0x18000f4ec  xor     r15d, r15d
0x18000f4ef  mov     esi, r15d
0x18000f4f2  test    rbx, rbx
0x18000f4f5  jz      loc_18000F5A5
0x18000f4fb  cmp     r14d, 2
0x18000f4ff  jb      loc_18000F5A5
0x18000f505  mov     ebp, r15d
0x18000f508  jmp     loc_18000F63B
0x18000f50d  cmp     r10, r12
0x18000f510  jz      short loc_18000F52D
0x18000f512  test    byte ptr [r10+1Ch], 8
0x18000f517  jz      short loc_18000F52D
0x18000f519  mov     rcx, [r10+10h]
0x18000f51d  mov     edx, 31h ; '1'
0x18000f522  mov     r9, rbx
0x18000f525  mov     r8, r13
0x18000f528  call    WPP_SF_S
0x18000f52d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f531  inc     rdi
0x18000f534  cmp     [rbx+rdi*2], r15w
0x18000f539  jnz     short loc_18000F531
0x18000f53b  lea     rdx, [rdi+1]; SizeInWords
0x18000f53f  mov     rcx, rbx; String
0x18000f542  call    cs:__imp__wcslwr_s
0x18000f548  test    eax, eax
0x18000f54a  jnz     loc_18000F5F9
0x18000f550  lea     rdx, aUrnSchemasMicr; "urn:schemas-microsoft-com:device:MediaC"...
0x18000f557  mov     rcx, rbx; Str
0x18000f55a  call    cs:__imp_wcsstr
0x18000f560  test    rax, rax
0x18000f563  jz      loc_18000F61D
0x18000f569  cmp     rax, rbx
0x18000f56c  jnz     loc_18000F61D
0x18000f572  mov     r10, cs:WPP_GLOBAL_Control
0x18000f579  cmp     r10, r12
0x18000f57c  jz      short loc_18000F5A0
0x18000f57e  test    byte ptr [r10+1Ch], 8
0x18000f583  jz      short loc_18000F5A0
0x18000f585  mov     rcx, [r10+10h]
0x18000f589  mov     edx, 32h ; '2'
0x18000f58e  mov     r9, rbx
0x18000f591  mov     r8, r13
0x18000f594  call    WPP_SF_S
0x18000f599  mov     r10, cs:WPP_GLOBAL_Control
0x18000f5a0  mov     esi, 1
0x18000f5a5  cmp     r10, r12
0x18000f5a8  jz      short loc_18000F5E6
0x18000f5aa  test    byte ptr [r10+1Ch], 8
0x18000f5af  jz      short loc_18000F5C9
0x18000f5b1  mov     rcx, [r10+10h]
0x18000f5b5  mov     edx, 34h ; '4'
0x18000f5ba  mov     r9d, esi
0x18000f5bd  call    WPP_SF_l
0x18000f5c2  mov     r10, cs:WPP_GLOBAL_Control
0x18000f5c9  cmp     r10, r12
0x18000f5cc  jz      short loc_18000F5E6
0x18000f5ce  test    byte ptr [r10+1Ch], 20h
0x18000f5d3  jz      short loc_18000F5E6
0x18000f5d5  mov     rcx, [r10+10h]
0x18000f5d9  mov     edx, 35h ; '5'
0x18000f5de  mov     r8, r13
0x18000f5e1  call    WPP_SF_
0x18000f5e6  mov     eax, esi
0x18000f5e8  add     rsp, 28h
0x18000f5ec  pop     r15
0x18000f5ee  pop     r14
0x18000f5f0  pop     r13
0x18000f5f2  pop     r12
0x18000f5f4  pop     rdi
0x18000f5f5  pop     rsi
0x18000f5f6  pop     rbp
0x18000f5f7  pop     rbx
0x18000f5f8  retn
0x18000f5f9  mov     r10, cs:WPP_GLOBAL_Control
0x18000f600  cmp     r10, r12
0x18000f603  jz      short loc_18000F624
0x18000f605  test    byte ptr [r10+1Ch], 2
0x18000f60a  jz      short loc_18000F624
0x18000f60c  mov     rcx, [r10+10h]
0x18000f610  mov     edx, 33h ; '3'
0x18000f615  mov     r8, r13
0x18000f618  call    WPP_SF_
0x18000f61d  mov     r10, cs:WPP_GLOBAL_Control
0x18000f624  lea     ecx, [rbp+1]
0x18000f627  add     rcx, rdi
0x18000f62a  cmp     rcx, r14
0x18000f62d  jnb     loc_18000F5A5
0x18000f633  inc     ebp
0x18000f635  add     ebp, edi
0x18000f637  lea     rbx, [rbx+rbp*2]
0x18000f63b  cmp     [rbx], r15w
0x18000f63f  jnz     loc_18000F50D
0x18000f645  jmp     loc_18000F5A5
```
