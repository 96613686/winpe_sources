# CCachePublication::WriteBufferredHashes(void)

- ea: `0x18008a44c`
- end: `0x18008a679`
- name: `?WriteBufferredHashes@CCachePublication@@AEAAKXZ`
- size: `557`
- prototype: `unsigned int __fastcall(CCachePublication *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180087750`
- `0x180089f00`

## callees

- `0x1800024fc`
- `0x180008290`
- `0x180011798`
- `0x18008a25c`
- `0x18008a44c`
- `0x18008ab1c`
- `0x180144882`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a56b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a56b`
- `KERNEL32!WriteFile` at `0x18008a55e`
- `KERNEL32!WriteFile` at `0x18008a55e`

## pseudocode

```c
__int64 __fastcall CCachePublication::WriteBufferredHashes(CCachePublication *this, __int64 a2, int a3)
{
  unsigned int v3; // edi
  const wchar_t *v5; // rdx
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rax
  DWORD v11; // r8d
  const void *v12; // rdx
  void *v13; // rcx
  char v14; // si
  void *v15; // rax
  void **v16; // r14
  void *v17; // rax
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v5 = L"Y";
    if ( !*((_BYTE *)this + 1864) )
      v5 = (const wchar_t *)L"N";
    WPP_SF_qSID(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      (_DWORD)v5,
      a3,
      (_DWORD)this,
      (__int64)v5,
      *((_QWORD *)this + 235),
      *((_DWORD *)this + 467));
  }
  if ( *((_BYTE *)this + 1864) )
  {
    LastError = CCachePublication::WaitForPendingWrite(this);
    v3 = LastError;
    if ( LastError )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 41;
LABEL_13:
        v9 = LastError;
LABEL_14:
        WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v9);
        return v3;
      }
      return v3;
    }
  }
  v10 = *((_QWORD *)this + 235);
  v11 = *((_DWORD *)this + 467);
  v12 = (const void *)*((_QWORD *)this + 232);
  *((_DWORD *)this + 450) = v10;
  v13 = (void *)*((_QWORD *)this + 214);
  *((_DWORD *)this + 451) = HIDWORD(v10);
  v14 = 1;
  if ( WriteFile(v13, v12, v11, &NumberOfBytesWritten, (LPOVERLAPPED)((char *)this + 1784)) )
  {
LABEL_18:
    if ( *((_BYTE *)this + 1864) )
    {
      if ( *((_BYTE *)this + 1848) )
      {
        v15 = (void *)*((_QWORD *)this + 229);
        v14 = 0;
      }
      else
      {
        v16 = (void **)((char *)this + 1840);
        if ( !*((_QWORD *)this + 230) )
        {
          v17 = operator new[](*((unsigned int *)this + 472));
          std::auto_ptr<unsigned short>::reset((char *)this + 1840, v17);
          memset_0(*v16, 0, *((unsigned int *)this + 472));
        }
        v15 = *v16;
      }
      *((_QWORD *)this + 232) = v15;
      *((_BYTE *)this + 1848) = v14;
    }
    else if ( NumberOfBytesWritten != *((_DWORD *)this + 467) )
    {
      v3 = 774;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 43;
        v9 = 774;
        goto LABEL_14;
      }
      return v3;
    }
    *((_QWORD *)this + 235) = 0;
    *((_DWORD *)this + 467) = 0;
    return v3;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError == 997 )
  {
    v3 = 0;
    *((_DWORD *)this + 468) = *((_DWORD *)this + 467);
    *((_BYTE *)this + 1864) = 1;
    goto LABEL_18;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v8 = 42;
    goto LABEL_13;
  }
  return v3;
}

```

## disassembly

```asm
0x18008a44c  mov     r11, rsp
0x18008a44f  mov     [r11+10h], rbx
0x18008a453  mov     [r11+18h], rsi
0x18008a457  push    rdi
0x18008a458  push    r14
0x18008a45a  push    r15
0x18008a45c  sub     rsp, 40h
0x18008a460  xor     edi, edi
0x18008a462  mov     rbx, rcx
0x18008a465  mov     [rsp+58h+NumberOfBytesWritten], edi
0x18008a469  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a470  lea     r15, WPP_GLOBAL_Control
0x18008a477  mov     r14b, 4
0x18008a47a  cmp     rcx, r15
0x18008a47d  jz      short loc_18008A4C9
0x18008a47f  test    [rcx+6Ch], r14b
0x18008a483  jz      short loc_18008A4C9
0x18008a485  cmp     [rcx+69h], r14b
0x18008a489  jb      short loc_18008A4C9
0x18008a48b  cmp     [rbx+748h], dil
0x18008a492  lea     rax, aN; "N"
0x18008a499  mov     rcx, [rcx+60h]
0x18008a49d  lea     rdx, aY; "Y"
0x18008a4a4  cmovz   rdx, rax
0x18008a4a8  mov     r9, rbx
0x18008a4ab  mov     eax, [rbx+74Ch]
0x18008a4b1  mov     [rsp+58h+var_28], eax
0x18008a4b5  mov     rax, [rbx+758h]
0x18008a4bc  mov     [r11-30h], rax
0x18008a4c0  mov     [r11-38h], rdx
0x18008a4c4  call    WPP_SF_qSID
0x18008a4c9  cmp     [rbx+748h], dil
0x18008a4d0  jz      short loc_18008A524
0x18008a4d2  mov     rcx, rbx; this
0x18008a4d5  call    ?WaitForPendingWrite@CCachePublication@@AEAAKXZ; CCachePublication::WaitForPendingWrite(void)
0x18008a4da  mov     edi, eax
0x18008a4dc  test    eax, eax
0x18008a4de  jz      short loc_18008A524
0x18008a4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a4e7  cmp     rcx, r15
0x18008a4ea  jz      loc_18008A62D
0x18008a4f0  test    [rcx+6Ch], r14b
0x18008a4f4  jz      loc_18008A62D
0x18008a4fa  mov     sil, 1
0x18008a4fd  cmp     [rcx+69h], sil
0x18008a501  jb      loc_18008A62D
0x18008a507  mov     edx, 29h ; ')'
0x18008a50c  mov     r9d, eax
0x18008a50f  mov     rcx, [rcx+60h]
0x18008a513  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008a51a  call    WPP_SF_d
0x18008a51f  jmp     loc_18008A62D
0x18008a524  mov     rax, [rbx+758h]
0x18008a52b  lea     rcx, [rbx+6F8h]
0x18008a532  mov     r8d, [rbx+74Ch]; nNumberOfBytesToWrite
0x18008a539  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008a53e  mov     rdx, [rbx+740h]; lpBuffer
0x18008a545  mov     [rcx+10h], eax
0x18008a548  shr     rax, 20h
0x18008a54c  mov     [rsp+58h+lpOverlapped], rcx; lpOverlapped
0x18008a551  mov     rcx, [rbx+6B0h]; hFile
0x18008a558  mov     [rbx+70Ch], eax
0x18008a55e  call    cs:__imp_WriteFile
0x18008a564  mov     sil, 1
0x18008a567  test    eax, eax
0x18008a569  jnz     short loc_18008A58F
0x18008a56b  call    cs:__imp_GetLastError
0x18008a571  mov     edi, eax
0x18008a573  cmp     eax, 3E5h
0x18008a578  jnz     short loc_18008A5B1
0x18008a57a  mov     eax, [rbx+74Ch]
0x18008a580  xor     edi, edi
0x18008a582  mov     [rbx+750h], eax
0x18008a588  mov     [rbx+748h], sil
0x18008a58f  cmp     byte ptr [rbx+748h], 0
0x18008a596  jz      loc_18008A643
0x18008a59c  cmp     byte ptr [rbx+738h], 0
0x18008a5a3  jz      short loc_18008A5D3
0x18008a5a5  mov     rax, [rbx+728h]
0x18008a5ac  xor     sil, sil
0x18008a5af  jmp     short loc_18008A60A
0x18008a5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a5b8  cmp     rcx, r15
0x18008a5bb  jz      short loc_18008A62D
0x18008a5bd  test    [rcx+6Ch], r14b
0x18008a5c1  jz      short loc_18008A62D
0x18008a5c3  cmp     [rcx+69h], sil
0x18008a5c7  jb      short loc_18008A62D
0x18008a5c9  mov     edx, 2Ah ; '*'
0x18008a5ce  jmp     loc_18008A50C
0x18008a5d3  lea     r14, [rbx+730h]
0x18008a5da  cmp     qword ptr [r14], 0
0x18008a5de  jnz     short loc_18008A607
0x18008a5e0  mov     ecx, [rbx+760h]; unsigned __int64
0x18008a5e6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008a5eb  mov     rdx, rax
0x18008a5ee  mov     rcx, r14
0x18008a5f1  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x18008a5f6  mov     r8d, [rbx+760h]; Size
0x18008a5fd  xor     edx, edx; Val
0x18008a5ff  mov     rcx, [r14]; void *
0x18008a602  call    memset_0
0x18008a607  mov     rax, [r14]
0x18008a60a  mov     [rbx+740h], rax
0x18008a611  mov     [rbx+738h], sil
0x18008a618  mov     qword ptr [rbx+758h], 0
0x18008a623  mov     dword ptr [rbx+74Ch], 0
0x18008a62d  mov     rbx, [rsp+58h+arg_8]
0x18008a632  mov     eax, edi
0x18008a634  mov     rsi, [rsp+58h+arg_10]
0x18008a639  add     rsp, 40h
0x18008a63d  pop     r15
0x18008a63f  pop     r14
0x18008a641  pop     rdi
0x18008a642  retn
0x18008a643  mov     eax, [rbx+74Ch]
0x18008a649  cmp     [rsp+58h+NumberOfBytesWritten], eax
0x18008a64d  jz      short loc_18008A618
0x18008a64f  mov     edi, 306h
0x18008a654  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a65b  cmp     rcx, r15
0x18008a65e  jz      short loc_18008A62D
0x18008a660  test    [rcx+6Ch], r14b
0x18008a664  jz      short loc_18008A62D
0x18008a666  cmp     [rcx+69h], sil
0x18008a66a  jb      short loc_18008A62D
0x18008a66c  mov     edx, 2Bh ; '+'
0x18008a671  mov     r9d, edi
0x18008a674  jmp     loc_18008A50F
```
