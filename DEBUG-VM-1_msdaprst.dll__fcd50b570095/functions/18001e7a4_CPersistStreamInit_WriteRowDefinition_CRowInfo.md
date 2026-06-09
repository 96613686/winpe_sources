# CPersistStreamInit::WriteRowDefinition(CRowInfo &)

- ea: `0x18001e7a4`
- end: `0x18001eafe`
- name: `?WriteRowDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18001e7a4`
- `0x18001f1a4`

## callees

- `0x180003abc`
- `0x1800041f8`
- `0x18001b728`
- `0x18001c6a4`
- `0x18001c818`
- `0x18001ca70`
- `0x18001e348`
- `0x18001e7a4`
- `0x18001edac`
- `0x18001f470`
- `0x18001f7ec`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteRowDefinition(CPersistStreamInit *this, void **a2)
{
  unsigned int v3; // edx
  __int64 result; // rax
  unsigned int v6; // eax
  _BYTE *v7; // rdx
  CPersistStreamInit *v8; // rcx
  bool v9; // r9
  __int64 v10; // r8
  bool v11; // r9
  unsigned __int16 v12; // di
  unsigned int v13; // r14d
  unsigned __int16 v14; // dx
  unsigned int v15; // [rsp+70h] [rbp+38h] BYREF

  v15 = 0;
  v3 = *((_DWORD *)this + 12);
  *((_DWORD *)this + 13) = 0;
  result = CPersistStreamInit::Indent(this, v3);
  if ( (int)result >= 0 )
  {
    result = CPersistStreamInit::WriteTag(this, 0x30u, &v15);
    if ( (int)result >= 0 )
    {
      result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
      if ( (int)result >= 0 )
      {
        result = CPersistStreamInit::WriteTag(this, 5u, &v15);
        if ( (int)result >= 0 )
        {
          result = CPersistStreamInit::WriteTag(this, 0x2Cu, &v15);
          if ( (int)result >= 0 )
          {
            result = CPersistStreamInit::WriteTag(this, 3u, &v15);
            if ( (int)result >= 0 )
            {
              result = CPersistStreamInit::WriteTag(this, 0x2Bu, &v15);
              if ( (int)result >= 0 )
              {
                result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                if ( (int)result >= 0 )
                {
                  v6 = CPersistStreamInit::_len(this, a2[20]);
                  result = CPersistStreamInit::Write(v8, v7, v6, &v15, 0);
                  if ( (int)result >= 0 )
                  {
                    result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                    if ( (int)result >= 0 )
                    {
                      result = CPersistStreamInit::WriteAttributeDefinition(
                                 this,
                                 *(void **)(*((_QWORD *)this + 9) + 880LL),
                                 *(unsigned __int16 **)(*((_QWORD *)this + 9) + 896LL),
                                 v9,
                                 0,
                                 0);
                      if ( (int)result >= 0 )
                      {
                        result = CPersistStreamInit::WriteRowsetMetaData(this, (struct CRowInfo *)a2, v10, v11);
                        if ( (int)result >= 0 )
                        {
                          result = CPersistStreamInit::WriteTag(this, 0x31u, &v15);
                          if ( (int)result >= 0 )
                          {
                            result = CPersistStreamInit::WriteTag(this, 0x28u, &v15);
                            if ( (int)result >= 0 )
                            {
                              v12 = 0;
                              ++*((_DWORD *)this + 12);
                              v13 = 0;
                              while ( v12 < *(_WORD *)a2 )
                              {
                                if ( (CMetaData::mdGetFlags((CMetaData *)a2, v12) & 0x2000) != 0
                                  || CMetaData::mdGetType((CMetaData *)a2, v14) == 136 )
                                {
                                  result = CPersistStreamInit::WriteRowDefinition(
                                             this,
                                             (struct CRowInfo *)((char *)a2[17] + 256 * (unsigned __int64)v13));
                                  if ( (int)result < 0 )
                                    return result;
                                  ++v13;
                                }
                                else
                                {
                                  result = CPersistStreamInit::WriteColumnDefinition(this, (struct CRowInfo *)a2, v12);
                                  if ( (int)result < 0 )
                                    return result;
                                }
                                ++v12;
                              }
                              CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
                              result = CPersistStreamInit::WriteTag(this, 0x30u, &v15);
                              if ( (int)result >= 0 )
                              {
                                result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
                                if ( (int)result >= 0 )
                                {
                                  result = CPersistStreamInit::WriteTag(this, 0xDu, &v15);
                                  if ( (int)result >= 0 )
                                  {
                                    result = CPersistStreamInit::WriteTag(this, 0x2Cu, &v15);
                                    if ( (int)result >= 0 )
                                    {
                                      result = CPersistStreamInit::WriteTag(this, 4u, &v15);
                                      if ( (int)result >= 0 )
                                      {
                                        result = CPersistStreamInit::WriteTag(this, 0x2Bu, &v15);
                                        if ( (int)result >= 0 )
                                        {
                                          result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                                          if ( (int)result >= 0 )
                                          {
                                            result = CPersistStreamInit::WriteNamespace(this, 0x41u);
                                            if ( (int)result >= 0 )
                                            {
                                              result = CPersistStreamInit::WriteTag(this, 0x23u, &v15);
                                              if ( (int)result >= 0 )
                                              {
                                                result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                                                if ( (int)result >= 0 )
                                                {
                                                  result = CPersistStreamInit::WriteTag(this, 0x32u, &v15);
                                                  if ( (int)result >= 0 )
                                                  {
                                                    result = CPersistStreamInit::WriteTag(this, 0x28u, &v15);
                                                    if ( (int)result >= 0 )
                                                    {
                                                      CPersistStreamInit::Indent(this, --*((_DWORD *)this + 12));
                                                      result = CPersistStreamInit::WriteTag(this, 0x33u, &v15);
                                                      if ( (int)result >= 0 )
                                                      {
                                                        result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
                                                        if ( (int)result >= 0 )
                                                        {
                                                          result = CPersistStreamInit::WriteTag(this, 5u, &v15);
                                                          if ( (int)result >= 0 )
                                                          {
                                                            result = CPersistStreamInit::WriteTag(this, 0x31u, &v15);
                                                            if ( (int)result >= 0 )
                                                              return CPersistStreamInit::WriteTag(this, 0x28u, &v15);
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e7a4  push    rbp
0x18001e7a6  push    rbx
0x18001e7a7  push    rsi
0x18001e7a8  push    rdi
0x18001e7a9  push    r12
0x18001e7ab  push    r14
0x18001e7ad  mov     rbp, rsp
0x18001e7b0  sub     rsp, 38h
0x18001e7b4  mov     rsi, rdx
0x18001e7b7  mov     [rbp+arg_0], 0
0x18001e7be  mov     edx, [rcx+30h]; unsigned int
0x18001e7c1  mov     rbx, rcx
0x18001e7c4  mov     dword ptr [rcx+34h], 0
0x18001e7cb  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001e7d0  test    eax, eax
0x18001e7d2  js      loc_18001EAF1
0x18001e7d8  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e7dc  mov     dl, 30h ; '0'; unsigned __int8
0x18001e7de  mov     rcx, rbx; this
0x18001e7e1  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e7e6  test    eax, eax
0x18001e7e8  js      loc_18001EAF1
0x18001e7ee  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001e7f0  mov     rcx, rbx; this
0x18001e7f3  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001e7f8  test    eax, eax
0x18001e7fa  js      loc_18001EAF1
0x18001e800  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e804  mov     dl, 5; unsigned __int8
0x18001e806  mov     rcx, rbx; this
0x18001e809  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e80e  test    eax, eax
0x18001e810  js      loc_18001EAF1
0x18001e816  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e81a  mov     dl, 2Ch ; ','; unsigned __int8
0x18001e81c  mov     rcx, rbx; this
0x18001e81f  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e824  test    eax, eax
0x18001e826  js      loc_18001EAF1
0x18001e82c  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e830  mov     dl, 3; unsigned __int8
0x18001e832  mov     rcx, rbx; this
0x18001e835  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e83a  test    eax, eax
0x18001e83c  js      loc_18001EAF1
0x18001e842  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e846  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001e848  mov     rcx, rbx; this
0x18001e84b  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e850  test    eax, eax
0x18001e852  js      loc_18001EAF1
0x18001e858  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e85c  mov     dl, 29h ; ')'; unsigned __int8
0x18001e85e  mov     rcx, rbx; this
0x18001e861  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e866  test    eax, eax
0x18001e868  js      loc_18001EAF1
0x18001e86e  mov     rdx, [rsi+0A0h]; void *
0x18001e875  mov     rcx, rbx; this
0x18001e878  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001e87d  mov     r8d, eax; Size
0x18001e880  mov     [rsp+38h+var_18], 0; bool
0x18001e885  lea     r9, [rbp+arg_0]; unsigned int *
0x18001e889  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001e88e  test    eax, eax
0x18001e890  js      loc_18001EAF1
0x18001e896  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e89a  mov     dl, 29h ; ')'; unsigned __int8
0x18001e89c  mov     rcx, rbx; this
0x18001e89f  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e8a4  test    eax, eax
0x18001e8a6  js      loc_18001EAF1
0x18001e8ac  mov     rdx, [rbx+48h]
0x18001e8b0  mov     rcx, rbx; this
0x18001e8b3  mov     [rsp+38h+var_10], 0; bool
0x18001e8b8  mov     [rsp+38h+var_18], 0; char
0x18001e8bd  mov     r8, [rdx+380h]; unsigned __int16 *
0x18001e8c4  mov     rdx, [rdx+370h]; void *
0x18001e8cb  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e8d0  test    eax, eax
0x18001e8d2  js      loc_18001EAF1
0x18001e8d8  mov     rdx, rsi; struct CRowInfo *
0x18001e8db  mov     rcx, rbx; this
0x18001e8de  call    ?WriteRowsetMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z; CPersistStreamInit::WriteRowsetMetaData(CRowInfo &)
0x18001e8e3  test    eax, eax
0x18001e8e5  js      loc_18001EAF1
0x18001e8eb  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e8ef  mov     dl, 31h ; '1'; unsigned __int8
0x18001e8f1  mov     rcx, rbx; this
0x18001e8f4  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e8f9  test    eax, eax
0x18001e8fb  js      loc_18001EAF1
0x18001e901  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e905  mov     dl, 28h ; '('; unsigned __int8
0x18001e907  mov     rcx, rbx; this
0x18001e90a  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e90f  test    eax, eax
0x18001e911  js      loc_18001EAF1
0x18001e917  mov     r12d, 1
0x18001e91d  xor     edi, edi
0x18001e91f  add     [rbx+30h], r12d
0x18001e923  xor     r14d, r14d
0x18001e926  cmp     di, [rsi]
0x18001e929  jnb     short loc_18001E98E
0x18001e92b  movzx   edx, di; unsigned __int16
0x18001e92e  mov     rcx, rsi; this
0x18001e931  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001e936  bt      eax, 0Dh
0x18001e93a  jb      short loc_18001E967
0x18001e93c  mov     rcx, rsi; this
0x18001e93f  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001e944  mov     ecx, 88h
0x18001e949  cmp     ax, cx
0x18001e94c  jz      short loc_18001E967
0x18001e94e  movzx   r8d, di; unsigned __int16
0x18001e952  mov     rdx, rsi; struct CRowInfo *
0x18001e955  mov     rcx, rbx; this
0x18001e958  call    ?WriteColumnDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z; CPersistStreamInit::WriteColumnDefinition(CRowInfo &,ushort)
0x18001e95d  test    eax, eax
0x18001e95f  js      loc_18001EAF1
0x18001e965  jmp     short loc_18001E988
0x18001e967  mov     edx, r14d
0x18001e96a  mov     rcx, rbx; this
0x18001e96d  shl     rdx, 8
0x18001e971  add     rdx, [rsi+88h]; struct CRowInfo *
0x18001e978  call    ?WriteRowDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z; CPersistStreamInit::WriteRowDefinition(CRowInfo &)
0x18001e97d  test    eax, eax
0x18001e97f  js      loc_18001EAF1
0x18001e985  add     r14d, r12d
0x18001e988  add     di, r12w
0x18001e98c  jmp     short loc_18001E926
0x18001e98e  mov     edx, [rbx+30h]; unsigned int
0x18001e991  mov     rcx, rbx; this
0x18001e994  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001e999  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e99d  mov     dl, 30h ; '0'; unsigned __int8
0x18001e99f  mov     rcx, rbx; this
0x18001e9a2  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e9a7  test    eax, eax
0x18001e9a9  js      loc_18001EAF1
0x18001e9af  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001e9b1  mov     rcx, rbx; this
0x18001e9b4  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001e9b9  test    eax, eax
0x18001e9bb  js      loc_18001EAF1
0x18001e9c1  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e9c5  mov     dl, 0Dh; unsigned __int8
0x18001e9c7  mov     rcx, rbx; this
0x18001e9ca  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e9cf  test    eax, eax
0x18001e9d1  js      loc_18001EAF1
0x18001e9d7  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e9db  mov     dl, 2Ch ; ','; unsigned __int8
0x18001e9dd  mov     rcx, rbx; this
0x18001e9e0  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e9e5  test    eax, eax
0x18001e9e7  js      loc_18001EAF1
0x18001e9ed  lea     r8, [rbp+arg_0]; unsigned int *
0x18001e9f1  mov     dl, 4; unsigned __int8
0x18001e9f3  mov     rcx, rbx; this
0x18001e9f6  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e9fb  test    eax, eax
0x18001e9fd  js      loc_18001EAF1
0x18001ea03  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ea07  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001ea09  mov     rcx, rbx; this
0x18001ea0c  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ea11  test    eax, eax
0x18001ea13  js      loc_18001EAF1
0x18001ea19  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ea1d  mov     dl, 29h ; ')'; unsigned __int8
0x18001ea1f  mov     rcx, rbx; this
0x18001ea22  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ea27  test    eax, eax
0x18001ea29  js      loc_18001EAF1
0x18001ea2f  mov     dl, 41h ; 'A'; unsigned __int8
0x18001ea31  mov     rcx, rbx; this
0x18001ea34  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001ea39  test    eax, eax
0x18001ea3b  js      loc_18001EAF1
0x18001ea41  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ea45  mov     dl, 23h ; '#'; unsigned __int8
0x18001ea47  mov     rcx, rbx; this
0x18001ea4a  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ea4f  test    eax, eax
0x18001ea51  js      loc_18001EAF1
0x18001ea57  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ea5b  mov     dl, 29h ; ')'; unsigned __int8
0x18001ea5d  mov     rcx, rbx; this
0x18001ea60  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ea65  test    eax, eax
0x18001ea67  js      loc_18001EAF1
0x18001ea6d  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ea71  mov     dl, 32h ; '2'; unsigned __int8
0x18001ea73  mov     rcx, rbx; this
0x18001ea76  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ea7b  test    eax, eax
0x18001ea7d  js      short loc_18001EAF1
0x18001ea7f  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ea83  mov     dl, 28h ; '('; unsigned __int8
0x18001ea85  mov     rcx, rbx; this
0x18001ea88  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ea8d  test    eax, eax
0x18001ea8f  js      short loc_18001EAF1
0x18001ea91  dec     dword ptr [rbx+30h]
0x18001ea94  mov     rcx, rbx; this
0x18001ea97  mov     edx, [rbx+30h]; unsigned int
0x18001ea9a  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001ea9f  lea     r8, [rbp+arg_0]; unsigned int *
0x18001eaa3  mov     dl, 33h ; '3'; unsigned __int8
0x18001eaa5  mov     rcx, rbx; this
0x18001eaa8  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001eaad  test    eax, eax
0x18001eaaf  js      short loc_18001EAF1
0x18001eab1  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001eab3  mov     rcx, rbx; this
0x18001eab6  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001eabb  test    eax, eax
0x18001eabd  js      short loc_18001EAF1
0x18001eabf  lea     r8, [rbp+arg_0]; unsigned int *
0x18001eac3  mov     dl, 5; unsigned __int8
0x18001eac5  mov     rcx, rbx; this
0x18001eac8  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001eacd  test    eax, eax
0x18001eacf  js      short loc_18001EAF1
0x18001ead1  lea     r8, [rbp+arg_0]; unsigned int *
0x18001ead5  mov     dl, 31h ; '1'; unsigned __int8
0x18001ead7  mov     rcx, rbx; this
0x18001eada  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001eadf  test    eax, eax
0x18001eae1  js      short loc_18001EAF1
0x18001eae3  lea     r8, [rbp+arg_0]; unsigned int *
0x18001eae7  mov     dl, 28h ; '('; unsigned __int8
0x18001eae9  mov     rcx, rbx; this
0x18001eaec  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001eaf1  add     rsp, 38h
0x18001eaf5  pop     r14
0x18001eaf7  pop     r12
0x18001eaf9  pop     rdi
0x18001eafa  pop     rsi
0x18001eafb  pop     rbx
0x18001eafc  pop     rbp
0x18001eafd  retn
```
