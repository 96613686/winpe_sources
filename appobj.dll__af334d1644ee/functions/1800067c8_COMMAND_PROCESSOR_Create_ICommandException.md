# COMMAND_PROCESSOR::Create(ICommandException * *)

- ea: `0x1800067c8`
- end: `0x18000695a`
- name: `?Create@COMMAND_PROCESSOR@@QEAAJPEAPEAVICommandException@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct ICommandException **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180013030`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x1800067c8`
- `0x18000dce8`
- `0x1800131d8`
- `0x180034cbe`
- `0x180034d00`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::Create(COMMAND_PROCESSOR *this, struct ICommandException **a2)
{
  _DWORD *v4; // rax
  int v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  va_list Arguments; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[32]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+50h] [rbp-B0h]
  __int16 v13; // [rsp+54h] [rbp-ACh]
  int v14; // [rsp+58h] [rbp-A8h]
  __int16 v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[510]; // [rsp+62h] [rbp-9Eh] BYREF

  memset_0(v16, 0, sizeof(v16));
  v12 = 512;
  v13 = 256;
  v11 = (unsigned __int16 *)&v15;
  v14 = 0;
  v15 = 0;
  Arguments = 0;
  v4 = operator new(0x50u);
  if ( v4 )
  {
    v4[2] = 1;
    *(_QWORD *)v4 = &OBJECT_EXTENSION_TABLE::`vftable';
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = &INTERNAL_EXTENSION_TABLE::`vftable';
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    v4[14] = 0;
    *((_QWORD *)v4 + 8) = 0;
    *((_QWORD *)v4 + 9) = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 26) = v4;
  if ( !v4 )
    goto LABEL_9;
  v5 = OBJECT_EXTENSION_TABLE::Create((OBJECT_EXTENSION_TABLE *)v4);
  if ( v5 < 0 && a2 )
  {
    v6 = operator new(0x58u);
    v7 = v6;
    if ( v6 )
    {
      v6[2] = 1;
      *(_QWORD *)v6 = &COMMAND_EXCEPTION::`vftable';
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = v6 + 4;
      v6[14] = 32;
      *((_WORD *)v6 + 30) = 256;
      v6[16] = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      v6[3] = v5;
      Arguments = 0;
      FormatCommandMessage(0xC0000415, &Arguments, (struct STRU *)v10);
      STRU::Copy((STRU *)(v7 + 4), (const unsigned __int8 *)v11);
      *a2 = (struct ICommandException *)v7;
      goto LABEL_10;
    }
LABEL_9:
    v5 = -2147024888;
  }
LABEL_10:
  BUFFER::~BUFFER((BUFFER *)v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800067c8  mov     [rsp-8+arg_10], rbx
0x1800067cd  mov     [rsp-8+arg_18], rsi
0x1800067d2  push    rbp
0x1800067d3  push    rdi
0x1800067d4  push    r14
0x1800067d6  lea     rbp, [rsp-170h]
0x1800067de  sub     rsp, 270h
0x1800067e5  mov     rax, cs:__security_cookie
0x1800067ec  xor     rax, rsp
0x1800067ef  mov     [rbp+180h+var_20], rax
0x1800067f6  mov     rsi, rdx
0x1800067f9  mov     rbx, rcx
0x1800067fc  xor     edx, edx; Val
0x1800067fe  lea     rcx, [rsp+280h+var_21E]; void *
0x180006803  mov     r8d, 1FEh; Size
0x180006809  call    memset_0
0x18000680e  xor     r14d, r14d
0x180006811  mov     [rsp+280h+var_230], 200h
0x180006819  lea     rax, [rsp+280h+var_220]
0x18000681e  mov     [rsp+280h+var_22C], 100h
0x180006825  mov     [rsp+280h+var_238], rax
0x18000682a  mov     [rsp+280h+var_228], r14d
0x18000682f  lea     ecx, [r14+50h]; Size
0x180006833  mov     [rsp+280h+var_220], r14w
0x180006839  mov     [rsp+280h+Arguments], r14
0x18000683e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006843  test    rax, rax
0x180006846  jz      short loc_180006882
0x180006848  mov     dword ptr [rax+8], 1
0x18000684f  lea     rcx, ??_7OBJECT_EXTENSION_TABLE@@6B@; const OBJECT_EXTENSION_TABLE::`vftable'
0x180006856  mov     [rax], rcx
0x180006859  lea     rcx, ??_7INTERNAL_EXTENSION_TABLE@@6B@; const INTERNAL_EXTENSION_TABLE::`vftable'
0x180006860  mov     [rax+10h], r14
0x180006864  mov     [rax+18h], r14
0x180006868  mov     [rax+20h], rcx
0x18000686c  mov     [rax+28h], r14
0x180006870  mov     [rax+30h], r14
0x180006874  mov     [rax+38h], r14d
0x180006878  mov     [rax+40h], r14
0x18000687c  mov     [rax+48h], r14
0x180006880  jmp     short loc_180006885
0x180006882  mov     rax, r14
0x180006885  mov     [rbx+0D0h], rax
0x18000688c  test    rax, rax
0x18000688f  jz      loc_180006922
0x180006895  mov     rcx, rax; this
0x180006898  call    ?Create@OBJECT_EXTENSION_TABLE@@QEAAJXZ; OBJECT_EXTENSION_TABLE::Create(void)
0x18000689d  mov     ebx, eax
0x18000689f  test    eax, eax
0x1800068a1  jns     loc_180006927
0x1800068a7  test    rsi, rsi
0x1800068aa  jz      short loc_180006927
0x1800068ac  mov     ecx, 58h ; 'X'; Size
0x1800068b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068b6  mov     rdi, rax
0x1800068b9  test    rax, rax
0x1800068bc  jz      short loc_180006922
0x1800068be  mov     dword ptr [rdi+8], 1
0x1800068c5  lea     rcx, [rdi+10h]
0x1800068c9  lea     rax, ??_7COMMAND_EXCEPTION@@6B@; const COMMAND_EXCEPTION::`vftable'
0x1800068d0  mov     [rdi], rax
0x1800068d3  lea     r8, [rsp+280h+var_258]; this
0x1800068d8  mov     [rcx], r14
0x1800068db  lea     rdx, [rsp+280h+Arguments]; Arguments
0x1800068e0  mov     [rcx+20h], rcx
0x1800068e4  mov     dword ptr [rcx+28h], 20h ; ' '
0x1800068eb  mov     word ptr [rcx+2Ch], 100h
0x1800068f1  mov     [rcx+30h], r14d
0x1800068f5  mov     ecx, 0C0000415h; dwMessageId
0x1800068fa  mov     [rdi+48h], r14
0x1800068fe  mov     [rdi+50h], r14
0x180006902  mov     [rdi+0Ch], ebx
0x180006905  mov     [rsp+280h+Arguments], r14
0x18000690a  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18000690f  mov     rdx, [rsp+280h+var_238]; unsigned __int16 *
0x180006914  lea     rcx, [rdi+10h]; this
0x180006918  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000691d  mov     [rsi], rdi
0x180006920  jmp     short loc_180006927
0x180006922  mov     ebx, 80070008h
0x180006927  lea     rcx, [rsp+280h+var_258]; this
0x18000692c  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180006931  mov     eax, ebx
0x180006933  mov     rcx, [rbp+180h+var_20]
0x18000693a  xor     rcx, rsp; StackCookie
0x18000693d  call    __security_check_cookie
0x180006942  lea     r11, [rsp+280h+var_10]
0x18000694a  mov     rbx, [r11+30h]
0x18000694e  mov     rsi, [r11+38h]
0x180006952  mov     rsp, r11
0x180006955  pop     r14
0x180006957  pop     rdi
0x180006958  pop     rbp
0x180006959  retn
```
