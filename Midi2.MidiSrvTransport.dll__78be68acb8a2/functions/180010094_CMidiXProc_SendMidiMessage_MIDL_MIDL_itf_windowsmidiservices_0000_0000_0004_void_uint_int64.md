# CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180010094`
- end: `0x180010259`
- name: `?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001389c`

## callees

- `0x180003004`
- `0x180007e24`
- `0x18000d0a4`
- `0x18000d7b8`
- `0x180010094`
- `0x180010260`

## pseudocode

```c
__int64 __fastcall CMidiXProc::SendMidiMessage(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        unsigned int a4,
        LARGE_INTEGER a5)
{
  _DWORD *v5; // rax
  const wchar_t *v6; // rbx
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // edi
  char v11; // r14
  const wchar_t *v12; // rbp
  __int64 v13; // rsi
  unsigned __int8 v14; // al
  int v15; // eax
  const char *v16; // rdx
  unsigned int v17; // esi
  int v19; // [rsp+20h] [rbp-68h]
  int v20; // [rsp+20h] [rbp-68h]
  _QWORD pExceptionObject[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = *(_DWORD **)(a1 + 112);
  v6 = a3;
  if ( !v5 )
  {
    v8 = -2147418113;
    v9 = 592;
    goto LABEL_28;
  }
  if ( a4 )
  {
    if ( *v5 == 1 )
    {
      if ( a4 > 0x800 )
      {
        v8 = -2147024809;
        v9 = 599;
        goto LABEL_28;
      }
    }
    else
    {
      if ( *v5 != 2 )
      {
        v8 = -2147024809;
        v9 = 595;
        goto LABEL_28;
      }
      if ( a4 > 0xAB0 )
      {
        v8 = -2147024809;
        v9 = 603;
        goto LABEL_28;
      }
    }
    v10 = v5[1] | a2;
    if ( (v10 & 8) != 0 )
    {
      v11 = v10 & 0xFE;
      pExceptionObject[1] = a3;
      v12 = &a3[2 * ((unsigned __int64)a4 >> 2)];
      pExceptionObject[2] = v12;
      while ( 1 )
      {
        pExceptionObject[0] = v6;
        if ( v6 >= v12 )
          break;
        if ( (v10 & 1) != 0 )
        {
          if ( v6 >= v12 )
            LODWORD(v13) = 0;
          else
            v13 = ((char *)v12 - (char *)v6) >> 2;
          if ( (_DWORD)v13 == WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject) )
            v11 = v10;
        }
        v14 = WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject);
        v15 = CMidiXProc::SendMidiMessageInternal(a1, v11, v6, 4 * (unsigned int)v14, a5);
        v17 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x275,
            (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
            (const char *)(unsigned int)v15,
            v20);
          return v17;
        }
        if ( v6 == v12 )
        {
          std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v16);
          throw (std::runtime_error *)pExceptionObject;
        }
        v6 += 2
            * WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject);
      }
    }
    else
    {
      v8 = CMidiXProc::SendMidiMessageInternal(a1, v10, a3, a4, a5);
      if ( v8 < 0 )
      {
        v9 = 634;
        goto LABEL_28;
      }
    }
    return 0;
  }
  v8 = -2147024809;
  v9 = 593;
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
    (const char *)(unsigned int)v8,
    v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010094  push    rbx
0x180010096  push    rbp
0x180010097  push    rsi
0x180010098  push    rdi
0x180010099  push    r12
0x18001009b  push    r14
0x18001009d  push    r15
0x18001009f  sub     rsp, 50h
0x1800100a3  mov     rax, [rcx+70h]
0x1800100a7  mov     rbx, r8
0x1800100aa  mov     edi, edx
0x1800100ac  mov     r15, rcx
0x1800100af  test    rax, rax
0x1800100b2  jz      loc_180010210
0x1800100b8  cmp     r9d, 1
0x1800100bc  jnb     short loc_1800100CD
0x1800100be  mov     ebx, 80070057h
0x1800100c3  mov     edx, 251h
0x1800100c8  jmp     loc_18001021A
0x1800100cd  cmp     dword ptr [rax], 1
0x1800100d0  jz      short loc_1800100FE
0x1800100d2  cmp     dword ptr [rax], 2
0x1800100d5  jz      short loc_1800100E6
0x1800100d7  mov     ebx, 80070057h
0x1800100dc  mov     edx, 253h
0x1800100e1  jmp     loc_18001021A
0x1800100e6  cmp     r9d, 0AB0h
0x1800100ed  jbe     short loc_180010116
0x1800100ef  mov     ebx, 80070057h
0x1800100f4  mov     edx, 25Bh
0x1800100f9  jmp     loc_18001021A
0x1800100fe  cmp     r9d, 800h
0x180010105  jbe     short loc_180010116
0x180010107  mov     ebx, 80070057h
0x18001010c  mov     edx, 257h
0x180010111  jmp     loc_18001021A
0x180010116  or      edi, [rax+4]
0x180010119  test    dil, 8
0x18001011d  jz      loc_1800101EB
0x180010123  mov     r12, qword ptr [rsp+88h+arg_20]
0x18001012b  mov     r14d, edi
0x18001012e  and     r14d, 0FFFFFFFEh
0x180010132  mov     eax, r9d
0x180010135  shr     rax, 2
0x180010139  mov     [rsp+88h+var_50], rbx
0x18001013e  lea     rbp, [r8+rax*4]
0x180010142  mov     [rsp+88h+var_48], rbp
0x180010147  mov     [rsp+88h+pExceptionObject], rbx
0x18001014c  cmp     rbx, rbp
0x18001014f  jnb     loc_18001020C
0x180010155  test    dil, 1
0x180010159  jz      short loc_180010181
0x18001015b  cmp     rbx, rbp
0x18001015e  jnb     short loc_18001016C
0x180010160  mov     rsi, rbp
0x180010163  sub     rsi, rbx
0x180010166  sar     rsi, 2
0x18001016a  jmp     short loc_18001016E
0x18001016c  xor     esi, esi
0x18001016e  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180010173  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x180010178  movzx   eax, al
0x18001017b  cmp     esi, eax
0x18001017d  cmovz   r14d, edi
0x180010181  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180010186  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18001018b  movzx   r9d, al
0x18001018f  mov     r8, rbx
0x180010192  shl     r9d, 2
0x180010196  mov     edx, r14d
0x180010199  mov     rcx, r15
0x18001019c  mov     qword ptr [rsp+88h+var_68], r12; int
0x1800101a1  call    ?SendMidiMessageInternal@CMidiXProc@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessageInternal(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x1800101a6  mov     esi, eax
0x1800101a8  test    eax, eax
0x1800101aa  js      short loc_1800101CB
0x1800101ac  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800101b1  cmp     rbx, rbp
0x1800101b4  jz      loc_180010242
0x1800101ba  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x1800101bf  movzx   eax, al
0x1800101c2  lea     rbx, [rbx+rax*4]
0x1800101c6  jmp     loc_180010147
0x1800101cb  mov     rcx, [rsp+88h]; this
0x1800101d3  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x1800101da  mov     r9d, esi; char *
0x1800101dd  mov     edx, 275h; void *
0x1800101e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800101e7  mov     eax, esi
0x1800101e9  jmp     short loc_180010233
0x1800101eb  mov     rax, qword ptr [rsp+88h+arg_20]
0x1800101f3  mov     edx, edi
0x1800101f5  mov     qword ptr [rsp+88h+var_68], rax
0x1800101fa  call    ?SendMidiMessageInternal@CMidiXProc@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessageInternal(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x1800101ff  mov     ebx, eax
0x180010201  test    eax, eax
0x180010203  jns     short loc_18001020C
0x180010205  mov     edx, 27Ah
0x18001020a  jmp     short loc_18001021A
0x18001020c  xor     eax, eax
0x18001020e  jmp     short loc_180010233
0x180010210  mov     ebx, 8000FFFFh
0x180010215  mov     edx, 250h; void *
0x18001021a  mov     rcx, [rsp+88h]; this
0x180010222  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x180010229  mov     r9d, ebx; char *
0x18001022c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010231  mov     eax, ebx
0x180010233  add     rsp, 50h
0x180010237  pop     r15
0x180010239  pop     r14
0x18001023b  pop     r12
0x18001023d  pop     rdi
0x18001023e  pop     rsi
0x18001023f  pop     rbp
0x180010240  pop     rbx
0x180010241  retn
0x180010242  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180010247  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001024e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180010253  call    _CxxThrowException_0
```
