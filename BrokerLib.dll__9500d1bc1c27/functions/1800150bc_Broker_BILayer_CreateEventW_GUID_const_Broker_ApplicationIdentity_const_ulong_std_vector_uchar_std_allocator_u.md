# Broker::BILayer::CreateEventW(_GUID const &,Broker::ApplicationIdentity const &,ulong,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800150bc`
- end: `0x1800151fe`
- name: `?CreateEventW@BILayer@Broker@@YA?AU_GUID@@AEBU3@AEBUApplicationIdentity@2@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `322`
- prototype: `_OWORD *__fastcall(_OWORD *, __int64, _QWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014f50`

## callees

- `0x180009e94`
- `0x1800150bc`
- `0x180015204`
- `0x1800165da`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180015102`
- `ntdll!RtlInitUnicodeString` at `0x180015102`
- `api-ms-win-core-bicltapi-l1-1-6!BiCreateEventForPackageName` at `0x180015139`
- `api-ms-win-core-bicltapi-l1-1-6!BiCreateEventForPackageName` at `0x180015139`

## pseudocode

```c
_OWORD *__fastcall Broker::BILayer::CreateEventW(_OWORD *a1, __int64 a2, _QWORD *a3, int a4, __int64 a5)
{
  const WCHAR *v5; // rbx
  bool v6; // zf
  const WCHAR *v11; // rdx
  struct _UNICODE_STRING *p_DestinationString; // r8
  __int64 v13; // rdx
  int EventForPackageName; // edi
  __int64 v15; // r8
  _QWORD *v16; // rcx
  char v18[8]; // [rsp+28h] [rbp-A0h]
  __int64 v19; // [rsp+30h] [rbp-98h]
  char v20[4]; // [rsp+40h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-78h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-68h] BYREF
  __int128 v23; // [rsp+68h] [rbp-60h]
  int v24; // [rsp+78h] [rbp-50h]
  int v25; // [rsp+80h] [rbp-48h]

  v5 = (const WCHAR *)(a3 + 7);
  *a1 = 0;
  v6 = a3[9] == 0;
  DestinationString = 0;
  if ( v6 )
  {
    p_DestinationString = 0;
  }
  else
  {
    if ( a3[10] <= 7u )
      v11 = (const WCHAR *)(a3 + 7);
    else
      v11 = *(const WCHAR **)v5;
    RtlInitUnicodeString(&DestinationString, v11);
    p_DestinationString = &DestinationString;
  }
  EventForPackageName = BiCreateEventForPackageName(
                          a1,
                          a2,
                          p_DestinationString,
                          *a3,
                          a4,
                          *(_QWORD *)a5,
                          *(_DWORD *)(a5 + 8) - (unsigned int)*(_QWORD *)a5);
  v16 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const WCHAR **)v5;
    *(_DWORD *)v20 = EventForPackageName;
    LODWORD(v19) = *(_DWORD *)(a5 + 8) - *(_DWORD *)a5;
    *(_DWORD *)v18 = a4;
    WPP_SF__sid_Sdd_guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      v15,
      (char *)*a3,
      v5,
      *(_QWORD *)v18,
      v19,
      a1,
      *(_DWORD *)v20);
    v16 = WPP_GLOBAL_Control;
  }
  if ( EventForPackageName < 0 )
  {
    if ( (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 2u )
      WPP_SF_d(v16[2], 11, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, (unsigned int)EventForPackageName);
    v24 = 6;
    v25 = EventForPackageName;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v23 = 0;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x1800150bc  push    rbx
0x1800150be  push    rbp
0x1800150bf  push    rsi
0x1800150c0  push    rdi
0x1800150c1  push    r14
0x1800150c3  push    r15
0x1800150c5  sub     rsp, 98h
0x1800150cc  xorps   xmm0, xmm0
0x1800150cf  lea     rbx, [r8+38h]
0x1800150d3  movups  xmmword ptr [rcx], xmm0
0x1800150d6  cmp     qword ptr [r8+48h], 0
0x1800150db  mov     ebp, r9d
0x1800150de  mov     r14, r8
0x1800150e1  mov     rdi, rdx
0x1800150e4  mov     rsi, rcx
0x1800150e7  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x1800150ec  jz      short loc_18001510F
0x1800150ee  cmp     qword ptr [rbx+18h], 7
0x1800150f3  jbe     short loc_1800150FA
0x1800150f5  mov     rdx, [rbx]
0x1800150f8  jmp     short loc_1800150FD
0x1800150fa  mov     rdx, rbx; SourceString
0x1800150fd  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x180015102  call    cs:__imp_RtlInitUnicodeString
0x180015108  lea     r8, [rsp+0C8h+DestinationString]
0x18001510d  jmp     short loc_180015112
0x18001510f  xor     r8d, r8d
0x180015112  mov     r15, [rsp+0C8h+arg_20]
0x18001511a  mov     rdx, rdi
0x18001511d  mov     r9, [r14]
0x180015120  mov     rcx, [r15]
0x180015123  mov     eax, [r15+8]
0x180015127  sub     eax, ecx
0x180015129  mov     dword ptr [rsp+0C8h+var_98], eax
0x18001512d  mov     qword ptr [rsp+0C8h+var_A0], rcx
0x180015132  mov     rcx, rsi
0x180015135  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x180015139  call    cs:__imp_BiCreateEventForPackageName
0x18001513f  mov     edi, eax
0x180015141  mov     rcx, cs:WPP_GLOBAL_Control
0x180015148  test    byte ptr [rcx+1Ch], 1
0x18001514c  jz      short loc_18001518E
0x18001514e  cmp     byte ptr [rcx+19h], 5
0x180015152  jb      short loc_18001518E
0x180015154  mov     eax, [r15+8]
0x180015158  sub     eax, [r15]
0x18001515b  cmp     qword ptr [rbx+18h], 7
0x180015160  jbe     short loc_180015165
0x180015162  mov     rbx, [rbx]
0x180015165  mov     r9, [r14]
0x180015168  mov     rcx, [rcx+10h]; LoggerHandle
0x18001516c  mov     dword ptr [rsp+0C8h+var_88], edi; char
0x180015170  mov     [rsp+0C8h+var_90], rsi; __int64
0x180015175  mov     dword ptr [rsp+0C8h+var_98], eax; char
0x180015179  mov     dword ptr [rsp+0C8h+var_A0], ebp; char
0x18001517d  mov     [rsp+0C8h+var_A8], rbx; __int64
0x180015182  call    WPP_SF__sid_Sdd_guid_d
0x180015187  mov     rcx, cs:WPP_GLOBAL_Control
0x18001518e  test    edi, edi
0x180015190  jns     short loc_1800151EB
0x180015192  test    byte ptr [rcx+1Ch], 1
0x180015196  jz      short loc_1800151B6
0x180015198  cmp     byte ptr [rcx+19h], 2
0x18001519c  jb      short loc_1800151B6
0x18001519e  mov     rcx, [rcx+10h]
0x1800151a2  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x1800151a9  mov     edx, 0Bh
0x1800151ae  mov     r9d, edi
0x1800151b1  call    WPP_SF_d
0x1800151b6  xorps   xmm0, xmm0
0x1800151b9  mov     [rsp+0C8h+var_50], 6
0x1800151c1  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x1800151c8  mov     [rsp+0C8h+var_48], edi
0x1800151cf  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x1800151d6  mov     [rsp+0C8h+pExceptionObject], rax
0x1800151db  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800151e0  movups  [rsp+0C8h+var_60], xmm0
0x1800151e5  call    _CxxThrowException_0
0x1800151eb  mov     rax, rsi
0x1800151ee  add     rsp, 98h
0x1800151f5  pop     r15
0x1800151f7  pop     r14
0x1800151f9  pop     rdi
0x1800151fa  pop     rsi
0x1800151fb  pop     rbp
0x1800151fc  pop     rbx
0x1800151fd  retn
```
