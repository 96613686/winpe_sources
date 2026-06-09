# Streaming::staging_operations::write_file(void const *,ulong,void *,ulong,ulong &)

- ea: `0x140011928`
- end: `0x140011a8a`
- name: `?write_file@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z`
- size: `354`
- prototype: `int __fastcall(Streaming::staging_operations *this, const void *, int *, void *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013f68`

## callees

- `0x14000935c`
- `0x140010104`
- `0x140011928`

## pseudocode

```c
int __fastcall Streaming::staging_operations::write_file(
        Streaming::staging_operations *this,
        const void *a2,
        int *a3,
        void *a4,
        _DWORD *a5)
{
  _DWORD *v5; // rsi
  unsigned int v6; // r14d
  unsigned int v8; // r10d
  int v10; // ecx
  int v11; // r8d
  unsigned int v12; // r9d
  __int64 v13; // rdx
  USHORT v14; // ax
  USHORT v15; // ax
  union _LARGE_INTEGER v16; // r8
  void *v17; // r9
  int result; // eax
  unsigned int v19; // [rsp+20h] [rbp-48h]
  unsigned int v20; // [rsp+28h] [rbp-40h]
  struct _UNICODE_STRING v21; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING v22; // [rsp+50h] [rbp-18h] BYREF

  v5 = a5;
  *(_DWORD *)(&v22.MaximumLength + 1) = 0;
  v6 = (unsigned int)a4;
  *(_DWORD *)(&v21.MaximumLength + 1) = 0;
  v8 = (unsigned int)a2;
  *a5 = 0;
  if ( !this )
    return -1073741811;
  if ( (unsigned int)a2 < 0x30 )
    return -1073741811;
  if ( (unsigned int)a2 < *((_DWORD *)this + 1) )
    return -1073741811;
  v10 = *((unsigned __int16 *)this + 6);
  if ( !(_WORD)v10 )
    return -1073741811;
  v11 = *((unsigned __int16 *)this + 10);
  if ( !(_WORD)v11 )
    return -1073741811;
  v12 = *((_DWORD *)this + 9);
  if ( !v12 )
    return -1073741811;
  v13 = (unsigned __int16)(*((__int64 *)this + 5) >> 63);
  if ( (unsigned __int16)(v13 + *((_QWORD *)this + 5)) != v13
    || *((_DWORD *)this + 2) + v10 > v8
    || *((_DWORD *)this + 4) + v11 > v8
    || !(unsigned __int8)messages::validate_pointer<_FILE_ALLOCATED_RANGE_BUFFER>(*((_QWORD *)this + 3), v12) )
  {
    return -1073741811;
  }
  v14 = *((_WORD *)this + 6);
  if ( v14 )
  {
    v22.Length = *((_WORD *)this + 6);
    v22.MaximumLength = v14;
    v22.Buffer = (PWSTR)((char *)this + *((unsigned int *)this + 2));
  }
  else
  {
    v22.Buffer = 0;
    *(_DWORD *)&v22.Length = 0;
  }
  v15 = *((_WORD *)this + 10);
  if ( v15 )
  {
    v21.Length = *((_WORD *)this + 10);
    v21.MaximumLength = v15;
    v21.Buffer = (PWSTR)((char *)this + *((unsigned int *)this + 4));
  }
  else
  {
    v21.Buffer = 0;
    *(_DWORD *)&v21.Length = 0;
  }
  v16 = *(union _LARGE_INTEGER *)((char *)this + 40);
  v17 = (void *)*((_QWORD *)this + 3);
  v19 = *((_DWORD *)this + 9);
  LODWORD(a5) = 0;
  result = Streaming::PackageWriter::WriteToStreamableFile(&v22, &v21, v16, v17, v19, v20, (unsigned int *)&a5);
  if ( v6 < 8 || !a3 )
    return -1073741811;
  a3[1] = (int)a5;
  *a3 = result;
  *v5 = 8;
  return result;
}

```

## disassembly

```asm
0x140011928  push    rbp
0x14001192a  push    rbx
0x14001192b  push    rsi
0x14001192c  push    rdi
0x14001192d  push    r14
0x14001192f  push    r15
0x140011931  mov     rbp, rsp
0x140011934  sub     rsp, 68h
0x140011938  mov     rsi, [rbp+arg_20]
0x14001193c  xor     r15d, r15d
0x14001193f  mov     dword ptr [rbp+var_18+4], r15d
0x140011943  mov     r14d, r9d
0x140011946  mov     dword ptr [rbp+var_28+4], r15d
0x14001194a  mov     rdi, r8
0x14001194d  mov     r10d, edx
0x140011950  mov     rbx, rcx
0x140011953  mov     [rsi], r15d
0x140011956  test    rcx, rcx
0x140011959  jz      loc_140011A77
0x14001195f  cmp     edx, 30h ; '0'
0x140011962  jb      loc_140011A77
0x140011968  cmp     edx, [rcx+4]
0x14001196b  jb      loc_140011A77
0x140011971  movzx   ecx, word ptr [rcx+0Ch]
0x140011975  test    cx, cx
0x140011978  jz      loc_140011A77
0x14001197e  movzx   r8d, word ptr [rbx+14h]
0x140011983  test    r8w, r8w
0x140011987  jz      loc_140011A77
0x14001198d  mov     r9d, [rbx+24h]
0x140011991  test    r9d, r9d
0x140011994  jz      loc_140011A77
0x14001199a  mov     rax, [rbx+28h]
0x14001199e  mov     r11d, 0FFFFh
0x1400119a4  cqo
0x1400119a6  and     rdx, r11
0x1400119a9  add     rax, rdx
0x1400119ac  and     rax, r11
0x1400119af  cmp     rax, rdx
0x1400119b2  jnz     loc_140011A77
0x1400119b8  mov     eax, ecx
0x1400119ba  add     eax, [rbx+8]
0x1400119bd  cmp     eax, r10d
0x1400119c0  ja      loc_140011A77
0x1400119c6  mov     eax, r8d
0x1400119c9  add     eax, [rbx+10h]
0x1400119cc  cmp     eax, r10d
0x1400119cf  ja      loc_140011A77
0x1400119d5  mov     rcx, [rbx+18h]
0x1400119d9  mov     edx, r9d
0x1400119dc  call    ??$validate_pointer@U_FILE_ALLOCATED_RANGE_BUFFER@@@messages@@YA_NPEAU_FILE_ALLOCATED_RANGE_BUFFER@@K@Z; messages::validate_pointer<_FILE_ALLOCATED_RANGE_BUFFER>(_FILE_ALLOCATED_RANGE_BUFFER *,ulong)
0x1400119e1  test    al, al
0x1400119e3  jz      loc_140011A77
0x1400119e9  movzx   eax, word ptr [rbx+0Ch]
0x1400119ed  test    ax, ax
0x1400119f0  jnz     short loc_1400119FC
0x1400119f2  mov     [rbp+var_18.Buffer], r15
0x1400119f6  mov     dword ptr [rbp+var_18.Length], r15d
0x1400119fa  jmp     short loc_140011A0E
0x1400119fc  mov     [rbp+var_18.Length], ax
0x140011a00  mov     [rbp+var_18.MaximumLength], ax
0x140011a04  mov     eax, [rbx+8]
0x140011a07  add     rax, rbx
0x140011a0a  mov     [rbp+var_18.Buffer], rax
0x140011a0e  movzx   eax, word ptr [rbx+14h]
0x140011a12  test    ax, ax
0x140011a15  jnz     short loc_140011A21
0x140011a17  mov     [rbp+var_28.Buffer], r15
0x140011a1b  mov     dword ptr [rbp+var_28.Length], r15d
0x140011a1f  jmp     short loc_140011A33
0x140011a21  mov     [rbp+var_28.Length], ax
0x140011a25  mov     [rbp+var_28.MaximumLength], ax
0x140011a29  mov     eax, [rbx+10h]
0x140011a2c  add     rax, rbx
0x140011a2f  mov     [rbp+var_28.Buffer], rax
0x140011a33  mov     r8, [rbx+28h]; union _LARGE_INTEGER
0x140011a37  lea     rax, [rbp+arg_20]
0x140011a3b  mov     r9, [rbx+18h]; void *
0x140011a3f  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x140011a43  mov     [rsp+68h+var_38], rax; unsigned int *
0x140011a48  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING *
0x140011a4c  mov     eax, [rbx+24h]
0x140011a4f  mov     [rsp+68h+var_48], eax; unsigned int
0x140011a53  mov     dword ptr [rbp+arg_20], r15d
0x140011a57  call    ?WriteToStreamableFile@PackageWriter@Streaming@@SAJAEBU_UNICODE_STRING@@0T_LARGE_INTEGER@@PEAXKIAEAK@Z; Streaming::PackageWriter::WriteToStreamableFile(_UNICODE_STRING const &,_UNICODE_STRING const &,_LARGE_INTEGER,void *,ulong,uint,ulong &)
0x140011a5c  cmp     r14d, 8
0x140011a60  jb      short loc_140011A77
0x140011a62  test    rdi, rdi
0x140011a65  jz      short loc_140011A77
0x140011a67  mov     ecx, dword ptr [rbp+arg_20]
0x140011a6a  mov     [rdi+4], ecx
0x140011a6d  mov     [rdi], eax
0x140011a6f  mov     dword ptr [rsi], 8
0x140011a75  jmp     short loc_140011A7C
0x140011a77  mov     eax, 0C000000Dh
0x140011a7c  add     rsp, 68h
0x140011a80  pop     r15
0x140011a82  pop     r14
0x140011a84  pop     rdi
0x140011a85  pop     rsi
0x140011a86  pop     rbx
0x140011a87  pop     rbp
0x140011a88  retn
```
