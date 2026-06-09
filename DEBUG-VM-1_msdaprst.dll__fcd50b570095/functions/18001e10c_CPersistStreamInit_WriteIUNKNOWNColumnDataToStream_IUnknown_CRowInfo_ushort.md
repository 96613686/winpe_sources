# CPersistStreamInit::WriteIUNKNOWNColumnDataToStream(IUnknown * *,CRowInfo &,ushort)

- ea: `0x18001e10c`
- end: `0x18001e340`
- name: `?WriteIUNKNOWNColumnDataToStream@CPersistStreamInit@@AEAAJPEAPEAUIUnknown@@AEAVCRowInfo@@G@Z`
- size: `564`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct IUnknown **, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001c994`

## callees

- `0x18000266c`
- `0x1800041f8`
- `0x18001ac00`
- `0x18001c36c`
- `0x18001e10c`
- `0x18002e02a`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `msvcrt!_ismbblead` at `0x18001e26d`
- `msvcrt!_ismbblead` at `0x18001e26d`
- `KERNEL32!MultiByteToWideChar` at `0x18001e2b9`
- `KERNEL32!MultiByteToWideChar` at `0x18001e2b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistStreamInit::WriteIUNKNOWNColumnDataToStream(
        CPersistStreamInit *this,
        struct IUnknown **a2,
        struct CRowInfo *a3,
        unsigned __int16 a4)
{
  struct IUnknown *v5; // rsi
  int v6; // ebx
  unsigned __int16 Type; // r15
  unsigned __int16 v8; // r15
  CHAR v9; // di
  unsigned int v10; // r12d
  CHAR *p_MultiByteStr; // rdx
  unsigned int v12; // ecx
  int v13; // eax
  unsigned __int16 v14; // r9
  unsigned int v15; // r8d
  unsigned __int16 *v16; // rdx
  int v17; // r14d
  int v18; // ebx
  char v19; // al
  int v20; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown **v24; // [rsp+40h] [rbp-C0h]
  CHAR MultiByteStr; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[1023]; // [rsp+51h] [rbp-AFh] BYREF
  WCHAR WideCharStr[1024]; // [rsp+450h] [rbp+350h] BYREF

  v24 = a2;
  v5 = *a2;
  v23 = 0;
  v22 = 0;
  v6 = 0;
  Type = CMetaData::mdGetType(a3, a4);
  if ( v5 )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v5->lpVtbl->QueryInterface)(
           v5,
           &IID_ISequentialStream,
           &v23) >= 0 )
    {
      v8 = Type & 0xBFFF;
      memset_0(&MultiByteStr, 0, 0x400u);
      v9 = 0;
      do
      {
        if ( v9 )
          MultiByteStr = v9;
        v10 = 1024 - (v9 != 0);
        p_MultiByteStr = v26;
        if ( !v9 )
          p_MultiByteStr = &MultiByteStr;
        v6 = (*(__int64 (__fastcall **)(__int64, CHAR *, _QWORD, unsigned int *))(*(_QWORD *)v23 + 24LL))(
               v23,
               p_MultiByteStr,
               v10,
               &v22);
        if ( v6 < 0 )
          break;
        v12 = v22;
        if ( v22 > v10 )
        {
          v6 = -2147467259;
          break;
        }
        if ( v22 )
        {
          if ( v8 == 128 )
          {
            v13 = CPersistStreamInit::BinaryOut(this, (unsigned __int8 *)&MultiByteStr, v22);
          }
          else
          {
            if ( v8 == 130 )
            {
              v14 = 130;
              v15 = v22 >> 1;
              v16 = (unsigned __int16 *)&MultiByteStr;
            }
            else
            {
              v17 = v22 + (v9 != 0);
              if ( v22 == v10 )
              {
                v18 = 1023;
                do
                {
                  if ( !_ismbblead((unsigned __int8)v26[v18 - 1]) )
                    break;
                  --v18;
                }
                while ( v18 );
                v19 = v18 + 1;
                if ( !v18 )
                  v19 = 0;
                if ( (-v19 & 1) != 0 )
                {
                  --v17;
                  v9 = v26[1022];
                }
                else
                {
                  v9 = 0;
                }
              }
              v20 = MultiByteToWideChar(0, 0, &MultiByteStr, v17, WideCharStr, 1024);
              v14 = v8;
              v15 = v20;
              v16 = WideCharStr;
            }
            v13 = CPersistStreamInit::TextOutW(this, v16, v15, v14);
          }
          v6 = v13;
          if ( v13 < 0 )
            break;
          v12 = v22;
        }
      }
      while ( v12 >= v10 );
    }
    ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
    *v24 = 0;
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e10c  mov     [rsp-8+arg_18], rbx
0x18001e111  push    rbp
0x18001e112  push    rsi
0x18001e113  push    rdi
0x18001e114  push    r12
0x18001e116  push    r13
0x18001e118  push    r14
0x18001e11a  push    r15
0x18001e11c  lea     rbp, [rsp-0B60h]
0x18001e124  sub     rsp, 0C60h
0x18001e12b  mov     rax, cs:__security_cookie
0x18001e132  xor     rax, rsp
0x18001e135  mov     [rbp+0B90h+var_40], rax
0x18001e13c  mov     [rsp+0C90h+var_C50], rdx
0x18001e141  mov     r13, rcx
0x18001e144  mov     rsi, [rdx]
0x18001e147  mov     [rsp+0C90h+var_C58], 0
0x18001e150  mov     [rsp+0C90h+var_C60], 0
0x18001e158  xor     ebx, ebx
0x18001e15a  movzx   edx, r9w; unsigned __int16
0x18001e15e  mov     rcx, r8; this
0x18001e161  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001e166  movzx   r15d, ax
0x18001e16a  test    rsi, rsi
0x18001e16d  jz      loc_18001E30A
0x18001e173  mov     rax, [rsi]
0x18001e176  lea     r8, [rsp+0C90h+var_C58]
0x18001e17b  lea     rdx, IID_ISequentialStream
0x18001e182  mov     rcx, rsi
0x18001e185  mov     rax, [rax]
0x18001e188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e18d  test    eax, eax
0x18001e18f  js      loc_18001E2EF
0x18001e195  mov     eax, 0BFFFh
0x18001e19a  and     r15w, ax
0x18001e19e  xor     edx, edx; Val
0x18001e1a0  mov     r8d, 400h; Size
0x18001e1a6  lea     rcx, [rsp+0C90h+MultiByteStr]; void *
0x18001e1ab  call    memset_0
0x18001e1b0  xor     dil, dil
0x18001e1b3  test    dil, dil
0x18001e1b6  jz      short loc_18001E1BD
0x18001e1b8  mov     [rsp+0C90h+MultiByteStr], dil
0x18001e1bd  xor     r14d, r14d
0x18001e1c0  test    dil, dil
0x18001e1c3  setnz   r14b
0x18001e1c7  mov     al, dil
0x18001e1ca  neg     al
0x18001e1cc  sbb     r12d, r12d
0x18001e1cf  add     r12d, 400h
0x18001e1d6  mov     rcx, [rsp+0C90h+var_C58]
0x18001e1db  mov     rax, [rcx]
0x18001e1de  lea     rdx, [rsp+0C90h+var_C3F]
0x18001e1e3  lea     r8, [rsp+0C90h+MultiByteStr]
0x18001e1e8  test    dil, dil
0x18001e1eb  cmovz   rdx, r8
0x18001e1ef  lea     r9, [rsp+0C90h+var_C60]
0x18001e1f4  mov     r8d, r12d
0x18001e1f7  mov     rax, [rax+18h]
0x18001e1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e200  mov     ebx, eax
0x18001e202  test    eax, eax
0x18001e204  js      loc_18001E2EF
0x18001e20a  mov     ecx, [rsp+0C90h+var_C60]
0x18001e20e  cmp     ecx, r12d
0x18001e211  ja      loc_18001E2EA
0x18001e217  test    ecx, ecx
0x18001e219  jz      loc_18001E2DF
0x18001e21f  mov     eax, 80h
0x18001e224  cmp     r15w, ax
0x18001e228  jnz     short loc_18001E23F
0x18001e22a  mov     r8d, ecx; unsigned int
0x18001e22d  lea     rdx, [rsp+0C90h+MultiByteStr]; unsigned __int8 *
0x18001e232  mov     rcx, r13; this
0x18001e235  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001e23a  jmp     loc_18001E2D5
0x18001e23f  mov     eax, 82h
0x18001e244  cmp     r15w, ax
0x18001e248  jnz     short loc_18001E259
0x18001e24a  mov     r9d, eax
0x18001e24d  shr     ecx, 1
0x18001e24f  mov     r8d, ecx
0x18001e252  lea     rdx, [rsp+0C90h+MultiByteStr]
0x18001e257  jmp     short loc_18001E2CD
0x18001e259  add     r14d, ecx
0x18001e25c  cmp     ecx, r12d
0x18001e25f  jnz     short loc_18001E299
0x18001e261  mov     ebx, 3FFh
0x18001e266  mov     eax, ebx
0x18001e268  movzx   ecx, [rsp+rax+0C90h+MultiByteStr]; Ch
0x18001e26d  call    cs:__imp__ismbblead
0x18001e273  test    eax, eax
0x18001e275  jz      short loc_18001E27C
0x18001e277  add     ebx, 0FFFFFFFFh
0x18001e27a  jnz     short loc_18001E266
0x18001e27c  lea     eax, [rbx+1]
0x18001e27f  test    ebx, ebx
0x18001e281  cmovz   eax, ebx
0x18001e284  neg     eax
0x18001e286  test    al, 1
0x18001e288  jnz     short loc_18001E28F
0x18001e28a  xor     dil, dil
0x18001e28d  jmp     short loc_18001E299
0x18001e28f  dec     r14d
0x18001e292  mov     dil, [rbp+0B90h+var_841]
0x18001e299  mov     [rsp+0C90h+cchWideChar], 400h; cchWideChar
0x18001e2a1  lea     rax, [rbp+0B90h+WideCharStr]
0x18001e2a8  mov     [rsp+0C90h+lpWideCharStr], rax; lpWideCharStr
0x18001e2ad  mov     r9d, r14d; cbMultiByte
0x18001e2b0  lea     r8, [rsp+0C90h+MultiByteStr]; lpMultiByteStr
0x18001e2b5  xor     edx, edx; dwFlags
0x18001e2b7  xor     ecx, ecx; CodePage
0x18001e2b9  call    cs:__imp_MultiByteToWideChar
0x18001e2bf  movzx   r9d, r15w; unsigned __int16
0x18001e2c3  mov     r8d, eax; unsigned int
0x18001e2c6  lea     rdx, [rbp+0B90h+WideCharStr]; unsigned __int16 *
0x18001e2cd  mov     rcx, r13; this
0x18001e2d0  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x18001e2d5  mov     ebx, eax
0x18001e2d7  test    eax, eax
0x18001e2d9  js      short loc_18001E2EF
0x18001e2db  mov     ecx, [rsp+0C90h+var_C60]
0x18001e2df  cmp     ecx, r12d
0x18001e2e2  jnb     loc_18001E1B3
0x18001e2e8  jmp     short loc_18001E2EF
0x18001e2ea  mov     ebx, 80004005h
0x18001e2ef  mov     rax, [rsi]
0x18001e2f2  mov     rcx, rsi
0x18001e2f5  mov     rax, [rax+10h]
0x18001e2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2fe  mov     rax, [rsp+0C90h+var_C50]
0x18001e303  mov     qword ptr [rax], 0
0x18001e30a  lea     rcx, [rsp+0C90h+var_C58]
0x18001e30f  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001e314  mov     eax, ebx
0x18001e316  mov     rcx, [rbp+0B90h+var_40]
0x18001e31d  xor     rcx, rsp; StackCookie
0x18001e320  call    __security_check_cookie
0x18001e325  mov     rbx, [rsp+0C90h+arg_18]
0x18001e32d  add     rsp, 0C60h
0x18001e334  pop     r15
0x18001e336  pop     r14
0x18001e338  pop     r13
0x18001e33a  pop     r12
0x18001e33c  pop     rdi
0x18001e33d  pop     rsi
0x18001e33e  pop     rbp
0x18001e33f  retn
```
