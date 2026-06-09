# CMidi2UmpProtocolDownscalerMidiTransform::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180010650`
- end: `0x1800108ef`
- name: `?SendMidiMessage@CMidi2UmpProtocolDownscalerMidiTransform@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `671`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *, unsigned int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008924`
- `0x18000b344`
- `0x18000b4d4`
- `0x18000d2f0`
- `0x18000dcc4`
- `0x18000de04`
- `0x18000e090`
- `0x180010650`
- `0x18001098c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800108cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800108cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001067c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001067c`

## string_xrefs

- `0x1800106ec`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18001083f`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::SendMidiMessage(
        __int64 a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int a4,
        int a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned __int64 v6; // r14
  int v10; // edi
  __int64 v11; // rdx
  unsigned __int64 v13; // r14
  _DWORD *v14; // r15
  unsigned int CurrentMessageWord; // eax
  unsigned int v16; // eax
  int v17; // edx
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // eax
  int v21; // [rsp+20h] [rbp-50h]
  int v22; // [rsp+20h] [rbp-50h]
  __int128 v23; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+50h] [rbp-20h]
  _QWORD v25[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned __int64 v27; // [rsp+A0h] [rbp+30h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  v6 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( *(_BYTE *)(a1 + 96) )
  {
    if ( (unsigned int)v6 < 4 )
    {
      v10 = -2147024809;
      v11 = 249;
      goto LABEL_8;
    }
    v13 = v6 >> 2;
    v24 = 0;
    v27 = v13;
    v23 = 0;
    if ( v13 )
      std::vector<unsigned int>::_Reallocate<0>(&v23, &v27);
    v14 = &a3[v13];
    v25[1] = a3;
    v25[2] = v14;
    while ( 1 )
    {
      v25[0] = a3;
      if ( a3 >= v14 )
        break;
      if ( *a3 >> 28 == 4 )
      {
        CurrentMessageWord = WindowsMidiServicesInternal::UmpBufferIterator::GetCurrentMessageWord(
                               (WindowsMidiServicesInternal::UmpBufferIterator *)v25,
                               0);
        umpToMIDI1Protocol::UMPStreamParse((umpToMIDI1Protocol *)(a1 + 56), CurrentMessageWord);
        v16 = WindowsMidiServicesInternal::UmpBufferIterator::GetCurrentMessageWord(
                (WindowsMidiServicesInternal::UmpBufferIterator *)v25,
                1u);
        umpToMIDI1Protocol::UMPStreamParse((umpToMIDI1Protocol *)(a1 + 56), v16);
        while ( *(_DWORD *)(a1 + 92) )
        {
          while ( 1 )
          {
            v17 = *(_DWORD *)(a1 + 92);
            if ( !v17 )
              break;
            v18 = *(int *)(a1 + 84);
            v19 = *(_DWORD *)(a1 + 4 * v18 + 68);
            *(_DWORD *)(a1 + 92) = v17 - 1;
            *(_DWORD *)(a1 + 84) = v18 + 1;
            if ( (_DWORD)v18 == 3 )
              *(_DWORD *)(a1 + 84) = 0;
            LODWORD(v27) = v19;
            if ( *((_QWORD *)&v23 + 1) == v24 )
            {
              std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v23, *((_QWORD *)&v23 + 1), &v27);
            }
            else
            {
              **((_DWORD **)&v23 + 1) = v19;
              *((_QWORD *)&v23 + 1) += 4LL;
            }
          }
        }
      }
      else
      {
        WindowsMidiServicesInternal::UmpBufferIterator::CopyCurrentMessageToVector(v25, &v23);
      }
      a3 += WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)v25);
    }
    v22 = a5;
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 136) + 24LL))(
            *(_QWORD *)(a1 + 136),
            a2,
            v23,
            (DWORD2(v23) - (_DWORD)v23) & 0xFFFFFFFC);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
        (const char *)(unsigned int)v20,
        v22);
      std::vector<unsigned int>::~vector<unsigned int>(&v23);
      goto LABEL_9;
    }
    std::vector<unsigned int>::~vector<unsigned int>(&v23);
    goto LABEL_30;
  }
  if ( !*(_BYTE *)(a1 + 97) )
  {
    v21 = a5;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, _QWORD))(**(_QWORD **)(a1 + 136) + 24LL))(
            *(_QWORD *)(a1 + 136),
            a2,
            a3,
            (unsigned int)v6);
    if ( v10 < 0 )
    {
      v11 = 243;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
        (const char *)(unsigned int)v10,
        v21);
LABEL_9:
      if ( v5 )
        LeaveCriticalSection(v5);
      return (unsigned int)v10;
    }
    goto LABEL_30;
  }
  if ( *(_BYTE *)(a1 + 97) )
  {
    v21 = a5;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, _QWORD))(**(_QWORD **)(a1 + 136) + 24LL))(
            *(_QWORD *)(a1 + 136),
            a2,
            a3,
            (unsigned int)v6);
    if ( v10 < 0 )
    {
      v11 = 302;
      goto LABEL_8;
    }
LABEL_30:
    if ( v5 )
      LeaveCriticalSection(v5);
    return 0;
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180010650  mov     [rsp-28h+arg_8], rbx
0x180010655  mov     [rsp-28h+arg_10], rsi
0x18001065a  push    rbp
0x18001065b  push    rdi
0x18001065c  push    r12
0x18001065e  push    r14
0x180010660  push    r15
0x180010662  mov     rbp, rsp
0x180010665  sub     rsp, 70h
0x180010669  lea     rbx, [rcx+10h]
0x18001066d  mov     r14d, r9d
0x180010670  mov     rsi, rcx
0x180010673  mov     rdi, r8
0x180010676  mov     rcx, rbx; lpCriticalSection
0x180010679  mov     r12d, edx
0x18001067c  call    cs:__imp_EnterCriticalSection
0x180010682  mov     cl, [rsi+60h]
0x180010685  test    cl, cl
0x180010687  jnz     short loc_1800106D8
0x180010689  cmp     [rsi+61h], cl
0x18001068c  jnz     short loc_1800106D0
0x18001068e  mov     rdx, [rsi+90h]
0x180010695  mov     r9d, r14d
0x180010698  mov     rcx, [rsi+88h]
0x18001069f  mov     r8, rdi
0x1800106a2  mov     [rsp+70h+var_48], rdx
0x1800106a7  mov     rdx, qword ptr [rbp+arg_20]
0x1800106ab  mov     qword ptr [rsp+70h+var_50], rdx
0x1800106b0  mov     edx, r12d
0x1800106b3  mov     rax, [rcx]
0x1800106b6  mov     rax, [rax+18h]
0x1800106ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106bf  mov     edi, eax
0x1800106c1  test    eax, eax
0x1800106c3  jns     loc_18001086A
0x1800106c9  mov     edx, 0F3h
0x1800106ce  jmp     short loc_1800106E8
0x1800106d0  test    cl, cl
0x1800106d2  jz      loc_18001087C
0x1800106d8  cmp     r14d, 4
0x1800106dc  jnb     short loc_180010710
0x1800106de  mov     edi, 80070057h
0x1800106e3  mov     edx, 0F9h; void *
0x1800106e8  mov     rcx, [rbp+28h]; this
0x1800106ec  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x1800106f3  mov     r9d, edi; char *
0x1800106f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106fb  test    rbx, rbx
0x1800106fe  jz      short loc_180010709
0x180010700  mov     rcx, rbx; lpCriticalSection
0x180010703  call    cs:__imp_LeaveCriticalSection
0x180010709  mov     eax, edi
0x18001070b  jmp     loc_1800108D6
0x180010710  shr     r14, 2
0x180010714  xorps   xmm0, xmm0
0x180010717  mov     [rbp+var_20], 0
0x18001071f  mov     [rbp+arg_0], r14
0x180010723  movdqu  [rbp+var_30], xmm0
0x180010728  test    r14, r14
0x18001072b  jz      short loc_18001073A
0x18001072d  lea     rdx, [rbp+arg_0]
0x180010731  lea     rcx, [rbp+var_30]
0x180010735  call    ??$_Reallocate@$0A@@?$vector@IV?$allocator@I@std@@@std@@AEAAXAEA_K@Z; std::vector<uint>::_Reallocate<0>(unsigned __int64 &)
0x18001073a  lea     r15, [rdi+r14*4]
0x18001073e  mov     [rbp+var_10], rdi
0x180010742  mov     [rbp+var_8], r15
0x180010746  mov     [rbp+var_18], rdi
0x18001074a  cmp     rdi, r15
0x18001074d  jnb     loc_1800107FB
0x180010753  mov     eax, [rdi]
0x180010755  lea     rcx, [rbp+var_18]; this
0x180010759  shr     eax, 1Ch
0x18001075c  cmp     al, 4
0x18001075e  jnz     short loc_1800107DD
0x180010760  xor     edx, edx; unsigned __int8
0x180010762  call    ?GetCurrentMessageWord@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAIE@Z; WindowsMidiServicesInternal::UmpBufferIterator::GetCurrentMessageWord(uchar)
0x180010767  mov     edx, eax; unsigned int
0x180010769  lea     rcx, [rsi+38h]; this
0x18001076d  call    ?UMPStreamParse@umpToMIDI1Protocol@@QEAAXI@Z; umpToMIDI1Protocol::UMPStreamParse(uint)
0x180010772  mov     dl, 1; unsigned __int8
0x180010774  lea     rcx, [rbp+var_18]; this
0x180010778  call    ?GetCurrentMessageWord@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAIE@Z; WindowsMidiServicesInternal::UmpBufferIterator::GetCurrentMessageWord(uchar)
0x18001077d  mov     edx, eax; unsigned int
0x18001077f  lea     rcx, [rsi+38h]; this
0x180010783  call    ?UMPStreamParse@umpToMIDI1Protocol@@QEAAXI@Z; umpToMIDI1Protocol::UMPStreamParse(uint)
0x180010788  cmp     dword ptr [rsi+5Ch], 0
0x18001078c  jz      short loc_1800107E6
0x18001078e  mov     edx, [rsi+5Ch]
0x180010791  test    edx, edx
0x180010793  jz      short loc_180010788
0x180010795  movsxd  rcx, dword ptr [rsi+54h]
0x180010799  lea     eax, [rdx-1]
0x18001079c  mov     r8d, [rsi+rcx*4+44h]
0x1800107a1  mov     [rsi+5Ch], eax
0x1800107a4  lea     eax, [rcx+1]
0x1800107a7  mov     [rsi+54h], eax
0x1800107aa  cmp     eax, 4
0x1800107ad  jnz     short loc_1800107B6
0x1800107af  mov     dword ptr [rsi+54h], 0
0x1800107b6  mov     rdx, qword ptr [rbp+var_30+8]
0x1800107ba  mov     dword ptr [rbp+arg_0], r8d
0x1800107be  cmp     rdx, [rbp+var_20]
0x1800107c2  jz      short loc_1800107CE
0x1800107c4  mov     [rdx], r8d
0x1800107c7  add     qword ptr [rbp+var_30+8], 4
0x1800107cc  jmp     short loc_18001078E
0x1800107ce  lea     r8, [rbp+arg_0]
0x1800107d2  lea     rcx, [rbp+var_30]
0x1800107d6  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800107db  jmp     short loc_18001078E
0x1800107dd  lea     rdx, [rbp+var_30]
0x1800107e1  call    ?CopyCurrentMessageToVector@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAXAEAV?$vector@IV?$allocator@I@std@@@std@@@Z; WindowsMidiServicesInternal::UmpBufferIterator::CopyCurrentMessageToVector(std::vector<uint> &)
0x1800107e6  lea     rcx, [rbp+var_18]; this
0x1800107ea  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x1800107ef  movzx   eax, al
0x1800107f2  lea     rdi, [rdi+rax*4]
0x1800107f6  jmp     loc_180010746
0x1800107fb  mov     rdx, [rsi+90h]
0x180010802  mov     rcx, [rsi+88h]
0x180010809  mov     r8, qword ptr [rbp+var_30]
0x18001080d  mov     r9, qword ptr [rbp+var_30+8]
0x180010811  mov     [rsp+70h+var_48], rdx
0x180010816  sub     r9, r8
0x180010819  mov     rdx, qword ptr [rbp+arg_20]
0x18001081d  and     r9d, 0FFFFFFFCh
0x180010821  mov     rax, [rcx]
0x180010824  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180010829  mov     edx, r12d
0x18001082c  mov     rax, [rax+18h]
0x180010830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010835  mov     edi, eax
0x180010837  test    eax, eax
0x180010839  jns     short loc_180010861
0x18001083b  mov     rcx, [rbp+28h]; this
0x18001083f  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x180010846  mov     r9d, eax; char *
0x180010849  mov     edx, 122h; void *
0x18001084e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010853  lea     rcx, [rbp+var_30]
0x180010857  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18001085c  jmp     loc_1800106FB
0x180010861  lea     rcx, [rbp+var_30]
0x180010865  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18001086a  test    rbx, rbx
0x18001086d  jz      short loc_180010878
0x18001086f  mov     rcx, rbx; lpCriticalSection
0x180010872  call    cs:__imp_LeaveCriticalSection
0x180010878  xor     eax, eax
0x18001087a  jmp     short loc_1800108D6
0x18001087c  cmp     byte ptr [rsi+61h], 0
0x180010880  jz      short loc_1800108C3
0x180010882  mov     rdx, [rsi+90h]
0x180010889  mov     r9d, r14d
0x18001088c  mov     rcx, [rsi+88h]
0x180010893  mov     r8, rdi
0x180010896  mov     [rsp+70h+var_48], rdx
0x18001089b  mov     rdx, qword ptr [rbp+arg_20]
0x18001089f  mov     qword ptr [rsp+70h+var_50], rdx
0x1800108a4  mov     edx, r12d
0x1800108a7  mov     rax, [rcx]
0x1800108aa  mov     rax, [rax+18h]
0x1800108ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108b3  mov     edi, eax
0x1800108b5  test    eax, eax
0x1800108b7  jns     short loc_18001086A
0x1800108b9  mov     edx, 12Eh
0x1800108be  jmp     loc_1800106E8
0x1800108c3  test    rbx, rbx
0x1800108c6  jz      short loc_1800108D1
0x1800108c8  mov     rcx, rbx; lpCriticalSection
0x1800108cb  call    cs:__imp_LeaveCriticalSection
0x1800108d1  mov     eax, 80004005h
0x1800108d6  lea     r11, [rsp+70h+var_s0]
0x1800108db  mov     rbx, [r11+38h]
0x1800108df  mov     rsi, [r11+40h]
0x1800108e3  mov     rsp, r11
0x1800108e6  pop     r15
0x1800108e8  pop     r14
0x1800108ea  pop     r12
0x1800108ec  pop     rdi
0x1800108ed  pop     rbp
0x1800108ee  retn
```
