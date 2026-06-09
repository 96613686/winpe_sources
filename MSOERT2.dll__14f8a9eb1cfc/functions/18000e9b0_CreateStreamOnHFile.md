# CreateStreamOnHFile

- ea: `0x18000e9b0`
- end: `0x18000ea95`
- name: `CreateStreamOnHFile`
- size: `229`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800092d4`
- `0x180009378`
- `0x18000e9b0`
- `0x18000eaa0`
- `0x180011fec`
- `0x180012fc0`

## pseudocode

```c
__int64 __fastcall CreateStreamOnHFile(
        char *a1,
        unsigned int a2,
        unsigned int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD a5,
        DWORD a6,
        void *a7,
        _QWORD *a8)
{
  unsigned int v12; // r9d
  __int64 v13; // r8
  int appended; // ebx
  WCHAR *v15; // rcx
  int v17; // [rsp+40h] [rbp-278h] BYREF
  WCHAR *v18; // [rsp+48h] [rbp-270h]
  unsigned __int16 v19[264]; // [rsp+60h] [rbp-258h] BYREF

  STRW::STRW((STRW *)&v17, v19, 0x104u);
  if ( !a1 )
    goto LABEL_5;
  v13 = -1;
  do
    ++v13;
  while ( a1[v13] );
  appended = STRW::AppendA_CCH_CP((STRW *)&v17, a1, v13, v12);
  if ( appended >= 0 )
  {
LABEL_5:
    v15 = (WCHAR *)&ExistingFileName;
    if ( v17 )
      v15 = v18;
    appended = CreateStreamOnHFileW(v15, a2, a3, a4, a5, a6, a7, a8);
  }
  STRW::~STRW((STRW *)&v17);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000e9b0  push    rbx
0x18000e9b2  push    rbp
0x18000e9b3  push    rsi
0x18000e9b4  push    rdi
0x18000e9b5  push    r14
0x18000e9b7  push    r15
0x18000e9b9  sub     rsp, 288h
0x18000e9c0  mov     rax, cs:__security_cookie
0x18000e9c7  xor     rax, rsp
0x18000e9ca  mov     [rsp+2B8h+var_48], rax
0x18000e9d2  mov     r14, [rsp+2B8h+arg_30]
0x18000e9da  mov     esi, r8d
0x18000e9dd  mov     r15, [rsp+2B8h+arg_38]
0x18000e9e5  mov     rbx, rcx
0x18000e9e8  mov     edi, edx
0x18000e9ea  lea     rcx, [rsp+2B8h+var_278]; this
0x18000e9ef  mov     r8d, 104h; unsigned int
0x18000e9f5  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x18000e9fa  mov     rbp, r9
0x18000e9fd  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000ea02  test    rbx, rbx
0x18000ea05  jz      short loc_18000EA28
0x18000ea07  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ea0b  inc     r8; unsigned int
0x18000ea0e  cmp     byte ptr [rbx+r8], 0
0x18000ea13  jnz     short loc_18000EA0B
0x18000ea15  mov     rdx, rbx; char *
0x18000ea18  lea     rcx, [rsp+2B8h+var_278]; this
0x18000ea1d  call    ?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z; STRW::AppendA_CCH_CP(char const *,ulong,uint)
0x18000ea22  mov     ebx, eax
0x18000ea24  test    eax, eax
0x18000ea26  js      short loc_18000EA69
0x18000ea28  mov     eax, [rsp+2B8h+arg_28]
0x18000ea2f  lea     rcx, ExistingFileName
0x18000ea36  cmp     [rsp+2B8h+var_278], 0
0x18000ea3b  mov     r9, rbp
0x18000ea3e  mov     [rsp+2B8h+var_280], r15
0x18000ea43  mov     r8d, esi
0x18000ea46  cmovnz  rcx, [rsp+2B8h+var_270]
0x18000ea4c  mov     edx, edi
0x18000ea4e  mov     [rsp+2B8h+var_288], r14
0x18000ea53  mov     [rsp+2B8h+var_290], eax
0x18000ea57  mov     eax, [rsp+2B8h+arg_20]
0x18000ea5e  mov     [rsp+2B8h+var_298], eax
0x18000ea62  call    CreateStreamOnHFileW
0x18000ea67  mov     ebx, eax
0x18000ea69  lea     rcx, [rsp+2B8h+var_278]; this
0x18000ea6e  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000ea73  mov     eax, ebx
0x18000ea75  mov     rcx, [rsp+2B8h+var_48]
0x18000ea7d  xor     rcx, rsp; StackCookie
0x18000ea80  call    __security_check_cookie
0x18000ea85  add     rsp, 288h
0x18000ea8c  pop     r15
0x18000ea8e  pop     r14
0x18000ea90  pop     rdi
0x18000ea91  pop     rsi
0x18000ea92  pop     rbp
0x18000ea93  pop     rbx
0x18000ea94  retn
```
