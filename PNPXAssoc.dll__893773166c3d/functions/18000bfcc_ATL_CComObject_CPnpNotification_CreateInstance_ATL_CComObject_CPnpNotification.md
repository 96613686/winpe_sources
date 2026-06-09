# ATL::CComObject<CPnpNotification>::CreateInstance(ATL::CComObject<CPnpNotification> * *)

- ea: `0x18000bfcc`
- end: `0x18000c13c`
- name: `?CreateInstance@?$CComObject@VCPnpNotification@@@ATL@@SAJPEAPEAV12@@Z`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a28c`

## callees

- `0x1800019d4`
- `0x180006f6c`
- `0x18000bce4`
- `0x18000bfcc`
- `0x18000c144`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpNotification>::CreateInstance(_QWORD *a1)
{
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  struct ATL::CAtlModule *v5; // rcx
  volatile signed __int32 *v6; // rsi
  signed __int32 v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  signed __int32 v10; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = operator new(0x90u);
  v4 = v3;
  if ( !v3 )
  {
    v9 = -2147024882;
    goto LABEL_24;
  }
  v3[2] = 0;
  *((_OWORD *)v3 + 1) = 0;
  *((_OWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 6) = 0;
  *((_BYTE *)v3 + 56) = 0;
  v3[16] = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  *((_QWORD *)v4 + 17) = v4 + 32;
  *((_QWORD *)v4 + 16) = v4 + 32;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  v5 = ATL::_pAtlModule;
  *(_QWORD *)v4 = &ATL::CComObject<CPnpNotification>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = v4 + 2;
  do
  {
    if ( *v6 == 0x7FFFFFFF )
      break;
    v7 = *v6;
  }
  while ( v7 != _InterlockedCompareExchange(v6, v7 + 1, v7) );
  v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v4 + 4));
  if ( v8 >= 0 )
  {
    *((_BYTE *)v4 + 56) = 1;
    v8 = CPnpNotification::FinalConstruct((CPnpNotification *)v4);
  }
  v9 = 0;
  if ( v8 < 0 )
    v9 = v8;
  do
  {
    if ( *v6 == 0x7FFFFFFF )
      break;
    v10 = *v6;
  }
  while ( v10 != _InterlockedCompareExchange(v6, v10 - 1, v10) );
  if ( v9 )
  {
    (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 48LL))(v4, 1);
LABEL_24:
    v4 = 0;
    goto LABEL_25;
  }
  v9 = 0;
LABEL_25:
  *a1 = v4;
  return v9;
}

```

## disassembly

```asm
0x18000bfcc  push    rbx
0x18000bfce  push    rsi
0x18000bfcf  push    rdi
0x18000bfd0  push    r14
0x18000bfd2  push    r15
0x18000bfd4  sub     rsp, 30h
0x18000bfd8  mov     r14, rcx
0x18000bfdb  test    rcx, rcx
0x18000bfde  jnz     short loc_18000BFEA
0x18000bfe0  mov     eax, 80004003h
0x18000bfe5  jmp     loc_18000C130
0x18000bfea  mov     qword ptr [rcx], 0
0x18000bff1  mov     ecx, 90h; Size
0x18000bff6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bffb  mov     rbx, rax
0x18000bffe  test    rax, rax
0x18000c001  jz      loc_18000C124
0x18000c007  mov     dword ptr [rax+8], 0
0x18000c00e  xorps   xmm0, xmm0
0x18000c011  movups  xmmword ptr [rbx+10h], xmm0
0x18000c015  xor     eax, eax
0x18000c017  movups  xmmword ptr [rbx+20h], xmm0
0x18000c01b  mov     [rbx+30h], rax
0x18000c01f  mov     [rbx+38h], al
0x18000c022  mov     [rbx+40h], eax
0x18000c025  mov     [rbx+70h], rax
0x18000c029  mov     [rbx+78h], rax
0x18000c02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c034  lea     rdi, WPP_GLOBAL_Control
0x18000c03b  cmp     rcx, rdi
0x18000c03e  jz      short loc_18000C05E
0x18000c040  cmp     byte ptr [rcx+19h], 4
0x18000c044  jb      short loc_18000C05E
0x18000c046  mov     rcx, [rcx+10h]
0x18000c04a  lea     edx, [rax+0Ah]
0x18000c04d  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c054  mov     [rsp+58h+var_38], rbx
0x18000c059  call    WPP_SF_sq
0x18000c05e  lea     rax, [rbx+80h]
0x18000c065  mov     [rbx+88h], rax
0x18000c06c  mov     [rax], rax
0x18000c06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c076  cmp     rcx, rdi
0x18000c079  jz      short loc_18000C09B
0x18000c07b  cmp     byte ptr [rcx+19h], 4
0x18000c07f  jb      short loc_18000C09B
0x18000c081  mov     rcx, [rcx+10h]
0x18000c085  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c08c  mov     edx, 0Bh
0x18000c091  mov     [rsp+58h+var_38], rbx
0x18000c096  call    WPP_SF_sq
0x18000c09b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c0a2  lea     rax, ??_7?$CComObject@VCPnpNotification@@@ATL@@6B@; const ATL::CComObject<CPnpNotification>::`vftable'
0x18000c0a9  mov     [rbx], rax
0x18000c0ac  mov     rax, [rcx]
0x18000c0af  mov     rax, [rax+8]
0x18000c0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b8  lea     rsi, [rbx+8]
0x18000c0bc  mov     r15d, 7FFFFFFFh
0x18000c0c2  jmp     short loc_18000C0CD
0x18000c0c4  lea     ecx, [rax+1]
0x18000c0c7  lock cmpxchg [rsi], ecx
0x18000c0cb  jz      short loc_18000C0D4
0x18000c0cd  mov     eax, [rsi]
0x18000c0cf  cmp     eax, r15d
0x18000c0d2  jnz     short loc_18000C0C4
0x18000c0d4  lea     rcx, [rsi+8]; this
0x18000c0d8  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000c0dd  test    eax, eax
0x18000c0df  js      short loc_18000C0ED
0x18000c0e1  mov     rcx, rbx; this
0x18000c0e4  mov     byte ptr [rsi+30h], 1
0x18000c0e8  call    ?FinalConstruct@CPnpNotification@@IEAAJXZ; CPnpNotification::FinalConstruct(void)
0x18000c0ed  xor     edi, edi
0x18000c0ef  test    eax, eax
0x18000c0f1  cmovs   edi, eax
0x18000c0f4  jmp     short loc_18000C0FF
0x18000c0f6  lea     ecx, [rax-1]
0x18000c0f9  lock cmpxchg [rsi], ecx
0x18000c0fd  jz      short loc_18000C106
0x18000c0ff  mov     eax, [rsi]
0x18000c101  cmp     eax, r15d
0x18000c104  jnz     short loc_18000C0F6
0x18000c106  test    edi, edi
0x18000c108  jz      short loc_18000C120
0x18000c10a  mov     rax, [rbx]
0x18000c10d  mov     edx, 1
0x18000c112  mov     rcx, rbx
0x18000c115  mov     rax, [rax+30h]
0x18000c119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c11e  jmp     short loc_18000C129
0x18000c120  xor     edi, edi
0x18000c122  jmp     short loc_18000C12B
0x18000c124  mov     edi, 8007000Eh
0x18000c129  xor     ebx, ebx
0x18000c12b  mov     [r14], rbx
0x18000c12e  mov     eax, edi
0x18000c130  add     rsp, 30h
0x18000c134  pop     r15
0x18000c136  pop     r14
0x18000c138  pop     rdi
0x18000c139  pop     rsi
0x18000c13a  pop     rbx
0x18000c13b  retn
```
