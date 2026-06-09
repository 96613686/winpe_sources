# KerbUnpackData

- ea: `0x180003730`
- end: `0x1800039ac`
- name: `KerbUnpackData`
- size: `636`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d60`
- `0x18000a1b0`
- `0x18000aed0`
- `0x18000b790`
- `0x18000c8c0`
- `0x18000cf30`
- `0x180014cec`

## callees

- `0x180003730`
- `0x1800146c4`
- `0x1800146ec`

## import_xrefs

- `MSASN1!ASN1_Decode` at `0x1800037b6`
- `MSASN1!ASN1_Decode` at `0x1800037b6`
- `MSASN1!ASN1_CreateDecoder` at `0x180003788`
- `MSASN1!ASN1_CreateDecoder` at `0x180003788`
- `MSASN1!ASN1_CloseDecoder` at `0x1800037d0`
- `MSASN1!ASN1_CloseDecoder` at `0x1800037d0`
- `MSASN1!ASN1_CreateModule` at `0x18000385b`
- `MSASN1!ASN1_CreateModule` at `0x18000385b`

## pseudocode

```c
__int64 __fastcall KerbUnpackData(__int64 a1, int a2, unsigned int a3, _QWORD *a4)
{
  __int64 Module; // rax
  unsigned int Decoder; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // esi
  PVOID *v15; // rcx
  PVOID *v16; // rcx
  _QWORD v17[9]; // [rsp+50h] [rbp-48h] BYREF

  v17[0] = 0;
  if ( !a2 || !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c655c859b2e13de8f31f421519d58447_Traceguids);
    return 60;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(0x10000, 1024, 4096, 81, off_18002A2E0, off_18002A050, off_18002A570, L"\b", 895644267);
    KRB5_Module = Module;
  }
  Decoder = ASN1_CreateDecoder(Module, v17, 0, 0, 0);
  if ( Decoder )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, Decoder);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
      {
        v11 = 60;
        WPP_SF_d(v15[2], 39, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 60);
        return v11;
      }
    }
    return 60;
  }
  v10 = v17[0];
  v11 = 0;
  *a4 = 0;
  v12 = ASN1_Decode(v10, a4, a3, 8, a1, a2);
  v13 = v12;
  if ( v12 < 0 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v12);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 == -1009 || v13 == -1002 )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
        WPP_SF_d(v16[2], 41, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, a3);
      v11 = -2147483647;
    }
    else
    {
      if ( v13 != -1011 && v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
        WPP_SF_d(v16[2], 42, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v13);
      v11 = 60;
    }
    *a4 = 0;
  }
  if ( v17[0] )
    ASN1_CloseDecoder();
  return v11;
}

```

## disassembly

```asm
0x180003730  push    rbx
0x180003732  push    rbp
0x180003733  push    rsi
0x180003734  push    rdi
0x180003735  push    r14
0x180003737  push    r15
0x180003739  sub     rsp, 68h
0x18000373d  xor     r15d, r15d
0x180003740  mov     r14, r9
0x180003743  mov     [rsp+98h+var_48], r15
0x180003748  mov     ebp, r8d
0x18000374b  mov     ebx, edx
0x18000374d  mov     rsi, rcx
0x180003750  test    edx, edx
0x180003752  jz      loc_1800037E5
0x180003758  test    rcx, rcx
0x18000375b  jz      loc_1800037E5
0x180003761  cmp     cs:?fKRB5ModuleStarted@@3HA, r15d; int fKRB5ModuleStarted
0x180003768  jz      loc_180003803
0x18000376e  mov     rax, cs:KRB5_Module
0x180003775  xor     r9d, r9d
0x180003778  mov     [rsp+98h+var_78], r15
0x18000377d  xor     r8d, r8d
0x180003780  lea     rdx, [rsp+98h+var_48]
0x180003785  mov     rcx, rax
0x180003788  call    cs:__imp_ASN1_CreateDecoder
0x18000378e  test    eax, eax
0x180003790  jnz     loc_18000386D
0x180003796  mov     rcx, [rsp+98h+var_48]
0x18000379b  mov     r9d, 8
0x1800037a1  mov     dword ptr [rsp+98h+var_70], ebx
0x1800037a5  mov     r8d, ebp
0x1800037a8  mov     rdx, r14
0x1800037ab  mov     [rsp+98h+var_78], rsi
0x1800037b0  mov     edi, r15d
0x1800037b3  mov     [r14], r15
0x1800037b6  call    cs:__imp_ASN1_Decode
0x1800037bc  mov     esi, eax
0x1800037be  test    eax, eax
0x1800037c0  js      loc_1800038DE
0x1800037c6  mov     rcx, [rsp+98h+var_48]
0x1800037cb  test    rcx, rcx
0x1800037ce  jz      short loc_1800037D6
0x1800037d0  call    cs:__imp_ASN1_CloseDecoder
0x1800037d6  mov     eax, edi
0x1800037d8  add     rsp, 68h
0x1800037dc  pop     r15
0x1800037de  pop     r14
0x1800037e0  pop     rdi
0x1800037e1  pop     rsi
0x1800037e2  pop     rbp
0x1800037e3  pop     rbx
0x1800037e4  retn
0x1800037e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037ec  lea     rbx, WPP_GLOBAL_Control
0x1800037f3  cmp     rcx, rbx
0x1800037f6  jnz     loc_180003988
0x1800037fc  mov     edi, 3Ch ; '<'
0x180003801  jmp     short loc_1800037D6
0x180003803  mov     [rsp+98h+var_58], 3562726Bh
0x18000380b  lea     rax, asc_18002D920; "\b"
0x180003812  mov     [rsp+98h+var_60], rax
0x180003817  mov     edx, 400h
0x18000381c  lea     rax, off_18002A570
0x180003823  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18000382d  mov     [rsp+98h+var_68], rax
0x180003832  mov     ecx, 10000h
0x180003837  lea     rax, off_18002A050
0x18000383e  mov     r9d, 51h ; 'Q'
0x180003844  mov     [rsp+98h+var_70], rax
0x180003849  mov     r8d, 1000h
0x18000384f  lea     rax, off_18002A2E0
0x180003856  mov     [rsp+98h+var_78], rax
0x18000385b  call    cs:__imp_ASN1_CreateModule
0x180003861  mov     cs:KRB5_Module, rax
0x180003868  jmp     loc_180003775
0x18000386d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003874  lea     rbx, WPP_GLOBAL_Control
0x18000387b  cmp     rcx, rbx
0x18000387e  jz      loc_1800037FC
0x180003884  test    byte ptr [rcx+1Ch], 1
0x180003888  jz      short loc_1800038A9
0x18000388a  mov     rcx, [rcx+10h]
0x18000388e  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180003895  mov     edx, 24h ; '$'
0x18000389a  mov     r9d, eax
0x18000389d  call    WPP_SF_d
0x1800038a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038a9  cmp     rcx, rbx
0x1800038ac  jz      loc_1800037FC
0x1800038b2  test    byte ptr [rcx+1Ch], 1
0x1800038b6  jz      loc_1800037FC
0x1800038bc  mov     rcx, [rcx+10h]
0x1800038c0  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800038c7  mov     edi, 3Ch ; '<'
0x1800038cc  mov     edx, 27h ; '''
0x1800038d1  mov     r9d, edi
0x1800038d4  call    WPP_SF_d
0x1800038d9  jmp     loc_1800037D6
0x1800038de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038e5  lea     rbx, WPP_GLOBAL_Control
0x1800038ec  cmp     rcx, rbx
0x1800038ef  jz      short loc_180003916
0x1800038f1  test    byte ptr [rcx+1Ch], 4
0x1800038f5  jz      short loc_180003916
0x1800038f7  mov     rcx, [rcx+10h]
0x1800038fb  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180003902  mov     edx, 28h ; '('
0x180003907  mov     r9d, esi
0x18000390a  call    WPP_SF_d
0x18000390f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003916  cmp     esi, 0FFFFFC0Fh
0x18000391c  jz      short loc_180003958
0x18000391e  cmp     esi, 0FFFFFC16h
0x180003924  jz      short loc_180003958
0x180003926  cmp     esi, 0FFFFFC0Dh
0x18000392c  jz      short loc_180003951
0x18000392e  cmp     rcx, rbx
0x180003931  jz      short loc_180003951
0x180003933  test    byte ptr [rcx+1Ch], 1
0x180003937  jz      short loc_180003951
0x180003939  mov     rcx, [rcx+10h]
0x18000393d  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180003944  mov     edx, 2Ah ; '*'
0x180003949  mov     r9d, esi
0x18000394c  call    WPP_SF_d
0x180003951  mov     edi, 3Ch ; '<'
0x180003956  jmp     short loc_180003980
0x180003958  cmp     rcx, rbx
0x18000395b  jz      short loc_18000397B
0x18000395d  test    byte ptr [rcx+1Ch], 4
0x180003961  jz      short loc_18000397B
0x180003963  mov     rcx, [rcx+10h]
0x180003967  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18000396e  mov     edx, 29h ; ')'
0x180003973  mov     r9d, ebp
0x180003976  call    WPP_SF_d
0x18000397b  mov     edi, 80000001h
0x180003980  mov     [r14], r15
0x180003983  jmp     loc_1800037C6
0x180003988  test    byte ptr [rcx+1Ch], 1
0x18000398c  jz      loc_1800037FC
0x180003992  mov     rcx, [rcx+10h]
0x180003996  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18000399d  mov     edx, 26h ; '&'
0x1800039a2  call    WPP_SF_
0x1800039a7  jmp     loc_1800037FC
```
