# COMMAND_PROCESSOR::SetLastConfigSectionException(long,ushort const *,INativeSectionException *,int)

- ea: `0x18000c800`
- end: `0x18000ca7d`
- name: `?SetLastConfigSectionException@COMMAND_PROCESSOR@@UEAAJJPEBGPEAVINativeSectionException@@H@Z`
- size: `637`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, int, const unsigned __int16 *, struct INativeSectionException *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x18000c800`
- `0x1800131d8`
- `0x180013288`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_ultow` at `0x18000c907`
- `msvcrt!_ultow` at `0x18000c907`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::SetLastConfigSectionException(
        COMMAND_PROCESSOR *this,
        int a2,
        const unsigned __int16 *a3,
        struct INativeSectionException *a4,
        int a5)
{
  signed int v9; // ebx
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int Value; // [rsp+20h] [rbp-E0h] BYREF
  va_list v16; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+60h] [rbp-A0h]
  __int16 v21; // [rsp+64h] [rbp-9Ch]
  int v22; // [rsp+68h] [rbp-98h]
  va_list Arguments[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+80h] [rbp-80h]
  wchar_t Buffer[64]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v26; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v27[510]; // [rsp+112h] [rbp+12h] BYREF

  v17 = 0;
  v16 = 0;
  Value = 0;
  *(_OWORD *)Arguments = 0;
  v24 = 0;
  memset_0(v27, 0, sizeof(v27));
  v20 = 512;
  v19 = (unsigned __int16 *)&v26;
  v21 = 256;
  v22 = 0;
  v26 = 0;
  if ( a4 && a3 )
  {
    if ( a5 || !*((_QWORD *)this + 26) )
    {
      v9 = (*(__int64 (__fastcall **)(struct INativeSectionException *, __int64 *))(*(_QWORD *)a4 + 24LL))(a4, &v17);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct INativeSectionException *, unsigned int *))(*(_QWORD *)a4 + 32LL))(
               a4,
               &Value);
        if ( v9 >= 0 )
        {
          _ultow(Value, Buffer, 10);
          v9 = (*(__int64 (__fastcall **)(struct INativeSectionException *, va_list *))(*(_QWORD *)a4 + 40LL))(a4, &v16);
          if ( v9 >= 0 )
          {
            Arguments[1] = v16;
            Arguments[0] = (va_list)a3;
            *(_QWORD *)&v24 = Buffer;
            *((_QWORD *)&v24 + 1) = v17;
            v9 = FormatCommandMessage(0xC00003E9, Arguments, (struct STRU *)v18);
            if ( v9 >= 0 )
            {
              v9 = StripWhiteSpace((struct STRU *)v18);
              if ( v9 >= 0 )
              {
                v10 = operator new(0x58u);
                v11 = v10;
                if ( v10 )
                {
                  *((_DWORD *)v10 + 2) = 1;
                  *v10 = &COMMAND_EXCEPTION::`vftable';
                  v10[2] = 0;
                  v10[6] = v10 + 2;
                  *((_DWORD *)v10 + 14) = 32;
                  *((_WORD *)v10 + 30) = 256;
                  *((_DWORD *)v10 + 16) = 0;
                  v10[9] = 0;
                  v10[10] = 0;
                  v12 = v10[9];
                  *((_DWORD *)v10 + 3) = a2;
                  if ( v12 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                  v11[9] = a4;
                  (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)a4 + 8LL))(a4);
                  v9 = STRU::Copy((STRU *)(v11 + 2), (const unsigned __int8 *)v19);
                  if ( v9 < 0 )
                  {
                    (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
                  }
                  else
                  {
                    v13 = *((_QWORD *)this + 26);
                    if ( v13 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                    *((_QWORD *)this + 26) = v11;
                  }
                }
                else
                {
                  v9 = -2147024888;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v9 = 1;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c800  mov     [rsp-8+arg_8], rbx
0x18000c805  mov     [rsp-8+arg_10], rsi
0x18000c80a  push    rbp
0x18000c80b  push    rdi
0x18000c80c  push    r12
0x18000c80e  push    r14
0x18000c810  push    r15
0x18000c812  lea     rbp, [rsp-220h]
0x18000c81a  sub     rsp, 320h
0x18000c821  mov     rax, cs:__security_cookie
0x18000c828  xor     rax, rsp
0x18000c82b  mov     [rbp+240h+var_30], rax
0x18000c832  xorps   xmm0, xmm0
0x18000c835  xor     r12d, r12d
0x18000c838  mov     rdi, r8
0x18000c83b  mov     [rsp+340h+var_310], r12
0x18000c840  mov     r15d, edx
0x18000c843  mov     [rsp+340h+var_318], r12
0x18000c848  mov     r14, rcx
0x18000c84b  mov     [rsp+340h+Value], r12d
0x18000c850  xor     edx, edx; Val
0x18000c852  lea     rcx, [rbp+240h+var_22E]; void *
0x18000c856  mov     r8d, 1FEh; Size
0x18000c85c  mov     rsi, r9
0x18000c85f  movups  xmmword ptr [rsp+340h+Arguments], xmm0
0x18000c864  movups  [rbp+240h+var_2C0], xmm0
0x18000c868  call    memset_0
0x18000c86d  mov     [rsp+340h+var_2E0], 200h
0x18000c875  lea     rax, [rbp+240h+var_230]
0x18000c879  mov     [rsp+340h+var_2E8], rax
0x18000c87e  mov     [rsp+340h+var_2DC], 100h
0x18000c885  mov     [rsp+340h+var_2D8], r12d
0x18000c88a  mov     [rbp+240h+var_230], r12w
0x18000c88f  test    rsi, rsi
0x18000c892  jz      loc_18000CA41
0x18000c898  test    rdi, rdi
0x18000c89b  jz      loc_18000CA41
0x18000c8a1  cmp     [rbp+240h+arg_20], r12d
0x18000c8a8  jnz     short loc_18000C8BD
0x18000c8aa  cmp     [r14+0D0h], r12
0x18000c8b1  jz      short loc_18000C8BD
0x18000c8b3  lea     ebx, [r12+1]
0x18000c8b8  jmp     loc_18000CA46
0x18000c8bd  mov     rax, [rsi]
0x18000c8c0  lea     rdx, [rsp+340h+var_310]
0x18000c8c5  mov     rcx, rsi
0x18000c8c8  mov     rax, [rax+18h]
0x18000c8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8d1  mov     ebx, eax
0x18000c8d3  test    eax, eax
0x18000c8d5  js      loc_18000CA46
0x18000c8db  mov     rax, [rsi]
0x18000c8de  lea     rdx, [rsp+340h+Value]
0x18000c8e3  mov     rcx, rsi
0x18000c8e6  mov     rax, [rax+20h]
0x18000c8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8ef  mov     ebx, eax
0x18000c8f1  test    eax, eax
0x18000c8f3  js      loc_18000CA46
0x18000c8f9  mov     ecx, [rsp+340h+Value]; Value
0x18000c8fd  lea     rdx, [rbp+240h+Buffer]; Buffer
0x18000c901  mov     r8d, 0Ah; Radix
0x18000c907  call    cs:__imp__ultow
0x18000c90d  mov     rax, [rsi]
0x18000c910  lea     rdx, [rsp+340h+var_318]
0x18000c915  mov     rcx, rsi
0x18000c918  mov     rax, [rax+28h]
0x18000c91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c921  mov     ebx, eax
0x18000c923  test    eax, eax
0x18000c925  js      loc_18000CA46
0x18000c92b  mov     rax, [rsp+340h+var_318]
0x18000c930  lea     r8, [rsp+340h+var_308]; this
0x18000c935  mov     [rsp+340h+Arguments+8], rax
0x18000c93a  lea     rdx, [rsp+340h+Arguments]; Arguments
0x18000c93f  lea     rax, [rbp+240h+Buffer]
0x18000c943  mov     [rsp+340h+Arguments], rdi
0x18000c948  mov     qword ptr [rbp+240h+var_2C0], rax
0x18000c94c  mov     ecx, 0C00003E9h; dwMessageId
0x18000c951  mov     rax, [rsp+340h+var_310]
0x18000c956  mov     qword ptr [rbp+240h+var_2C0+8], rax
0x18000c95a  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18000c95f  mov     ebx, eax
0x18000c961  test    eax, eax
0x18000c963  js      loc_18000CA46
0x18000c969  lea     rcx, [rsp+340h+var_308]; this
0x18000c96e  call    ?StripWhiteSpace@@YAJPEAVSTRU@@@Z; StripWhiteSpace(STRU *)
0x18000c973  mov     ebx, eax
0x18000c975  test    eax, eax
0x18000c977  js      loc_18000CA46
0x18000c97d  mov     ecx, 58h ; 'X'; Size
0x18000c982  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c987  mov     rdi, rax
0x18000c98a  test    rax, rax
0x18000c98d  jz      loc_18000CA3A
0x18000c993  mov     dword ptr [rdi+8], 1
0x18000c99a  lea     rcx, [rdi+10h]
0x18000c99e  lea     rax, ??_7COMMAND_EXCEPTION@@6B@; const COMMAND_EXCEPTION::`vftable'
0x18000c9a5  mov     [rdi], rax
0x18000c9a8  mov     [rcx], r12
0x18000c9ab  mov     [rcx+20h], rcx
0x18000c9af  mov     dword ptr [rcx+28h], 20h ; ' '
0x18000c9b6  mov     word ptr [rcx+2Ch], 100h
0x18000c9bc  mov     [rcx+30h], r12d
0x18000c9c0  mov     [rdi+48h], r12
0x18000c9c4  mov     [rdi+50h], r12
0x18000c9c8  mov     rcx, [rdi+48h]
0x18000c9cc  mov     [rdi+0Ch], r15d
0x18000c9d0  test    rcx, rcx
0x18000c9d3  jz      short loc_18000C9E1
0x18000c9d5  mov     rax, [rcx]
0x18000c9d8  mov     rax, [rax+10h]
0x18000c9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9e1  mov     [rdi+48h], rsi
0x18000c9e5  mov     rcx, rsi
0x18000c9e8  mov     rax, [rsi]
0x18000c9eb  mov     rax, [rax+8]
0x18000c9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f4  mov     rdx, [rsp+340h+var_2E8]; unsigned __int16 *
0x18000c9f9  lea     rcx, [rdi+10h]; this
0x18000c9fd  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ca02  mov     ebx, eax
0x18000ca04  test    eax, eax
0x18000ca06  js      short loc_18000CA29
0x18000ca08  mov     rcx, [r14+0D0h]
0x18000ca0f  test    rcx, rcx
0x18000ca12  jz      short loc_18000CA20
0x18000ca14  mov     rax, [rcx]
0x18000ca17  mov     rax, [rax+10h]
0x18000ca1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca20  mov     [r14+0D0h], rdi
0x18000ca27  jmp     short loc_18000CA46
0x18000ca29  mov     rax, [rdi]
0x18000ca2c  mov     rcx, rdi
0x18000ca2f  mov     rax, [rax+10h]
0x18000ca33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca38  jmp     short loc_18000CA46
0x18000ca3a  mov     ebx, 80070008h
0x18000ca3f  jmp     short loc_18000CA46
0x18000ca41  mov     ebx, 80070057h
0x18000ca46  lea     rcx, [rsp+340h+var_308]; this
0x18000ca4b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ca50  mov     eax, ebx
0x18000ca52  mov     rcx, [rbp+240h+var_30]
0x18000ca59  xor     rcx, rsp; StackCookie
0x18000ca5c  call    __security_check_cookie
0x18000ca61  lea     r11, [rsp+340h+var_20]
0x18000ca69  mov     rbx, [r11+38h]
0x18000ca6d  mov     rsi, [r11+40h]
0x18000ca71  mov     rsp, r11
0x18000ca74  pop     r15
0x18000ca76  pop     r14
0x18000ca78  pop     r12
0x18000ca7a  pop     rdi
0x18000ca7b  pop     rbp
0x18000ca7c  retn
```
