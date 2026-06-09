# XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(_EVENT_TRACE const *)

- ea: `0x18001e314`
- end: `0x18001e440`
- name: `?ParseEvent@CProviderBinaryPathEvent@XPerfAddIn@@QEAAJPEBU_EVENT_TRACE@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this, const struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001da60`

## callees

- `0x180002420`
- `0x180007da8`
- `0x18001aac0`
- `0x18001e314`

## pseudocode

```c
__int64 __fastcall XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this,
        const struct _EVENT_TRACE *a2)
{
  __int64 result; // rax
  unsigned __int64 MofLength; // rsi
  unsigned int *MofData; // r13
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdi
  __int64 v8; // r14
  __int64 v9; // rdx
  char *v10; // r15
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r12
  unsigned __int64 v13; // rsi
  unsigned __int64 i; // r8
  ATL::CAtlException *v15; // [rsp+20h] [rbp-38h] BYREF

  if ( !a2->MofData )
    return 262403;
  MofLength = a2->MofLength;
  if ( MofLength < 4 )
    return 262403;
  MofData = (unsigned int *)a2->MofData;
  v6 = MofLength - 4;
  v7 = *MofData;
  v8 = 16 * v7;
  if ( v6 < 16 * v7 )
    return 262403;
  try
  {
    v9 = *(_QWORD *)this;
    v10 = (char *)*((_QWORD *)this + 1);
    v11 = (__int64)&v10[-*(_QWORD *)this] >> 4;
    if ( v7 >= v11 )
    {
      if ( v7 > v11 )
      {
        if ( v7 <= (*((_QWORD *)this + 2) - v9) >> 4 )
        {
          v12 = v7 - v11;
          if ( v7 != v11 )
          {
            LOBYTE(v9) = 0;
            memset_0(v10, v9, 16 * v12);
            do
            {
              v10 += 16;
              --v12;
            }
            while ( v12 );
          }
          *((_QWORD *)this + 1) = v10;
        }
        else
        {
          std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(this, *MofData);
        }
      }
    }
    else
    {
      *((_QWORD *)this + 1) = v9 + v8;
    }
    v13 = v6 - v8;
    for ( i = 0; i < v7; ++i )
      *(_OWORD *)(*(_QWORD *)this + 16 * i) = *(_OWORD *)&MofData[4 * i + 1];
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      (char *)this + 24,
      &MofData[(unsigned __int64)v8 / 4 + 1],
      (unsigned int)(v13 >> 1));
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v15 )
  {
    return *(unsigned int *)v15;
  }
  v9 = *(_QWORD *)this;
}

```

## disassembly

```asm
0x18001e314  mov     [rsp+arg_0], rbx
0x18001e319  mov     [rsp+arg_10], rsi
0x18001e31e  push    rdi
0x18001e31f  push    r12
0x18001e321  push    r13
0x18001e323  push    r14
0x18001e325  push    r15
0x18001e327  sub     rsp, 30h
0x18001e32b  mov     rbx, rcx
0x18001e32e  cmp     qword ptr [rdx+48h], 0
0x18001e333  jnz     short loc_18001E33F
0x18001e335  mov     eax, 40103h
0x18001e33a  jmp     loc_18001E427
0x18001e33f  mov     esi, [rdx+50h]
0x18001e342  cmp     rsi, 4
0x18001e346  jnb     short loc_18001E352
0x18001e348  mov     eax, 40103h
0x18001e34d  jmp     loc_18001E427
0x18001e352  mov     r13, [rdx+48h]
0x18001e356  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18001e35a  mov     edi, [r13+0]
0x18001e35e  mov     r14d, edi
0x18001e361  shl     r14, 4
0x18001e365  cmp     rsi, r14
0x18001e368  jnb     short loc_18001E374
0x18001e36a  mov     eax, 40103h
0x18001e36f  jmp     loc_18001E427
0x18001e374  mov     rdx, [rcx]
0x18001e377  mov     r15, [rcx+8]
0x18001e37b  mov     rcx, r15
0x18001e37e  sub     rcx, rdx
0x18001e381  sar     rcx, 4
0x18001e385  cmp     rdi, rcx
0x18001e388  jnb     short loc_18001E394
0x18001e38a  lea     rax, [rdx+r14]
0x18001e38e  mov     [rbx+8], rax
0x18001e392  jmp     short loc_18001E3DA
0x18001e394  jbe     short loc_18001E3DA
0x18001e396  mov     rax, [rbx+10h]
0x18001e39a  sub     rax, rdx
0x18001e39d  sar     rax, 4
0x18001e3a1  cmp     rdi, rax
0x18001e3a4  jbe     short loc_18001E3B3
0x18001e3a6  mov     rdx, rdi
0x18001e3a9  mov     rcx, rbx
0x18001e3ac  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001e3b1  jmp     short loc_18001E3DA
0x18001e3b3  mov     r12, rdi
0x18001e3b6  sub     r12, rcx
0x18001e3b9  jz      short loc_18001E3D6
0x18001e3bb  mov     r8, r12
0x18001e3be  shl     r8, 4; Size
0x18001e3c2  xor     dl, dl; Val
0x18001e3c4  mov     rcx, r15; void *
0x18001e3c7  call    memset_0
0x18001e3cc  add     r15, 10h
0x18001e3d0  sub     r12, 1
0x18001e3d4  jnz     short loc_18001E3CC
0x18001e3d6  mov     [rbx+8], r15
0x18001e3da  lea     rdx, [r13+4]
0x18001e3de  add     rdx, r14
0x18001e3e1  sub     rsi, r14
0x18001e3e4  xor     r8d, r8d
0x18001e3e7  test    rdi, rdi
0x18001e3ea  jz      short loc_18001E408
0x18001e3ec  mov     rcx, r8
0x18001e3ef  add     rcx, rcx
0x18001e3f2  mov     rax, [rbx]
0x18001e3f5  movups  xmm0, xmmword ptr [r13+rcx*8+4]
0x18001e3fb  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18001e400  inc     r8
0x18001e403  cmp     r8, rdi
0x18001e406  jb      short loc_18001E3EC
0x18001e408  shr     rsi, 1
0x18001e40b  lea     rcx, [rbx+18h]
0x18001e40f  mov     r8d, esi
0x18001e412  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e417  nop
0x18001e418  xor     eax, eax
0x18001e41a  jmp     short loc_18001E427
0x18001e41c  mov     eax, [rsp+58h+arg_8]
0x18001e420  jmp     short loc_18001E427
0x18001e422  mov     eax, 8007000Eh
0x18001e427  mov     rbx, [rsp+58h+arg_0]
0x18001e42c  mov     rsi, [rsp+58h+arg_10]
0x18001e431  add     rsp, 30h
0x18001e435  pop     r15
0x18001e437  pop     r14
0x18001e439  pop     r13
0x18001e43b  pop     r12
0x18001e43d  pop     rdi
0x18001e43e  retn
```
