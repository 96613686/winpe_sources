# GetWinReGuid

- ea: `0x180118fd4`
- end: `0x1801193ea`
- name: `GetWinReGuid`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180118418`

## callees

- `0x180010cc0`
- `0x1800aa134`
- `0x1800aa1a4`
- `0x1800d3940`
- `0x1800eb920`
- `0x1800ef360`
- `0x180118fd4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18011911a`
- `ntdll!RtlAllocateHeap` at `0x18011911a`
- `ntdll!RtlFreeHeap` at `0x1801192a9`
- `ntdll!RtlFreeHeap` at `0x18011933f`
- `ntdll!RtlFreeHeap` at `0x1801192a9`
- `ntdll!RtlFreeHeap` at `0x18011933f`
- `bcd!BcdOpenObject` at `0x1801190ba`
- `bcd!BcdOpenObject` at `0x1801191ed`
- `bcd!BcdOpenObject` at `0x1801190ba`
- `bcd!BcdOpenObject` at `0x1801191ed`
- `bcd!BcdCloseObject` at `0x18011907e`
- `bcd!BcdCloseObject` at `0x180119244`
- `bcd!BcdCloseObject` at `0x1801192c7`
- `bcd!BcdCloseObject` at `0x18011931d`
- `bcd!BcdCloseObject` at `0x18011935d`
- `bcd!BcdCloseObject` at `0x1801193ca`
- `bcd!BcdCloseObject` at `0x18011907e`
- `bcd!BcdCloseObject` at `0x180119244`
- `bcd!BcdCloseObject` at `0x1801192c7`
- `bcd!BcdCloseObject` at `0x18011931d`
- `bcd!BcdCloseObject` at `0x18011935d`
- `bcd!BcdCloseObject` at `0x1801193ca`
- `bcd!BcdGetElementDataWithFlags` at `0x1801190f1`
- `bcd!BcdGetElementDataWithFlags` at `0x1801190f1`
- `bcd!BcdOpenSystemStore` at `0x18011902a`
- `bcd!BcdOpenSystemStore` at `0x18011902a`
- `bcd!BcdGetElementData` at `0x180119176`
- `bcd!BcdGetElementData` at `0x180119219`
- `bcd!BcdGetElementData` at `0x180119176`
- `bcd!BcdGetElementData` at `0x180119219`

## pseudocode

```c
__int64 __fastcall GetWinReGuid(__int64 a1, _OWORD *a2)
{
  __int64 InitPointer; // rax
  int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v9; // rax
  _OWORD *Heap; // rax
  _OWORD *v11; // rbx
  int ElementData; // eax
  __int64 v13; // r8
  int v14; // edi
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // edi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  const char *v24; // [rsp+30h] [rbp-19h] BYREF
  const char *v25; // [rsp+38h] [rbp-11h]
  __int64 v26; // [rsp+40h] [rbp-9h]
  const char *v27; // [rsp+48h] [rbp-1h]
  SIZE_T Size; // [rsp+50h] [rbp+7h] BYREF
  __int64 v29; // [rsp+58h] [rbp+Fh] BYREF
  int v30; // [rsp+60h] [rbp+17h] BYREF
  __int16 v31; // [rsp+64h] [rbp+1Bh] BYREF
  void *v32; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v33; // [rsp+70h] [rbp+27h] BYREF
  __int128 v34; // [rsp+78h] [rbp+2Fh] BYREF

  v30 = 0;
  v32 = 0;
  v29 = 0;
  v31 = 0;
  LODWORD(Size) = 0;
  v34 = 0;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v32);
  v4 = BcdOpenSystemStore(InitPointer);
  if ( v4 < 0 )
  {
    v26 = 237;
LABEL_3:
    v24 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    v25 = "GetWinReGuid";
    v27 = "Status";
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v30,
           &v24,
           (unsigned int)v4);
LABEL_4:
    v7 = v5;
    if ( v29 )
    {
      BcdCloseObject(v29, v6);
      v29 = 0;
    }
    if ( v32 )
      CloseBcdStore(v32);
    return v7;
  }
  v9 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v29);
  v4 = BcdOpenObject(v32, &GUID_CURRENT_BOOT_ENTRY, v9);
  if ( v4 < 0 )
  {
    v26 = 244;
    goto LABEL_3;
  }
  BcdGetElementDataWithFlags(v29, 335544328, 0, 0, &Size);
  if ( (unsigned int)Size < 0x10uLL )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801193E9LL);
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
  v11 = Heap;
  if ( !Heap )
  {
    v26 = 254;
    v24 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    v27 = "RecoveryGuids.AllocateBytes(BufferSize)";
    v25 = "GetWinReGuid";
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v30,
           &v24);
    goto LABEL_4;
  }
  ElementData = BcdGetElementData(v29, 335544328, Heap, &Size);
  if ( ElementData >= 0 )
  {
    v14 = 0;
    if ( (Size & 0xFFFFFFF0) != 0 )
    {
      while ( 1 )
      {
        v33 = 0;
        v34 = v11[v14];
        v15 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v33);
        v16 = BcdOpenObject(v32, &v34, v15);
        if ( v16 < 0 )
          break;
        LODWORD(Size) = 2;
        v17 = BcdGetElementData(v33, 1174405136, &v31, &Size);
        v18 = Size;
        if ( v17 >= 0 && (_DWORD)Size == 2 && (_BYTE)v31 )
        {
          v22 = v33;
          *a2 = v34;
          if ( v22 )
          {
            ((void (*)(void))BcdCloseObject)();
            v33 = 0;
          }
          LOBYTE(v23) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
          if ( !v23 )
            __fastfail(7u);
          if ( v29 )
          {
            ((void (*)(void))BcdCloseObject)();
            v29 = 0;
          }
          if ( v32 )
            CloseBcdStore(v32);
          return 0;
        }
        if ( v33 )
        {
          BcdCloseObject(v33, (unsigned int)Size);
          v18 = Size;
        }
        if ( ++v14 >= v18 >> 4 )
          goto LABEL_24;
      }
      v26 = 275;
      v24 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v25 = "GetWinReGuid";
      v27 = "Status";
      v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v30,
              &v24,
              (unsigned int)v16);
      if ( v33 )
      {
        ((void (*)(void))BcdCloseObject)();
        v33 = 0;
      }
      goto LABEL_26;
    }
LABEL_24:
    v26 = 296;
    v24 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    v13 = 3221225487LL;
    v27 = 0;
    v25 = "GetWinReGuid";
  }
  else
  {
    v26 = 262;
    v24 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    v13 = (unsigned int)ElementData;
    v25 = "GetWinReGuid";
    v27 = "Status";
  }
  v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
          &v30,
          &v24,
          v13);
LABEL_26:
  LOBYTE(v20) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( !v20 )
    __fastfail(7u);
  if ( v29 )
  {
    BcdCloseObject(v29, v21);
    v29 = 0;
  }
  if ( v32 )
    CloseBcdStore(v32);
  return v19;
}

```

## disassembly

```asm
0x180118fd4  mov     [rsp-8+arg_0], rbx
0x180118fd9  mov     [rsp-8+arg_10], rsi
0x180118fde  push    rbp
0x180118fdf  push    rdi
0x180118fe0  push    r14
0x180118fe2  lea     rbp, [rsp-47h]
0x180118fe7  sub     rsp, 90h
0x180118fee  mov     rax, cs:__security_cookie
0x180118ff5  xor     rax, rsp
0x180118ff8  mov     [rbp+57h+var_18], rax
0x180118ffc  xor     r14d, r14d
0x180118fff  lea     rcx, [rbp+57h+var_38]
0x180119003  xorps   xmm0, xmm0
0x180119006  mov     [rbp+57h+var_40], r14d
0x18011900a  mov     [rbp+57h+var_38], r14
0x18011900e  mov     rsi, rdx
0x180119011  mov     [rbp+57h+var_48], r14
0x180119015  mov     [rbp+57h+var_3C], r14w
0x18011901a  mov     dword ptr [rbp+57h+Size], r14d
0x18011901e  movups  [rbp+57h+var_28], xmm0
0x180119022  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180119027  mov     rcx, rax
0x18011902a  call    cs:__imp_BcdOpenSystemStore
0x180119031  nop     dword ptr [rax+rax+00h]
0x180119036  test    eax, eax
0x180119038  jns     short loc_1801190A3
0x18011903a  mov     [rbp+57h+var_60], 0EDh
0x180119042  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180119049  mov     r8d, eax
0x18011904c  mov     [rbp+57h+var_70], rcx
0x180119050  lea     rdx, [rbp+57h+var_70]
0x180119054  lea     rcx, aGetwinreguid; "GetWinReGuid"
0x18011905b  mov     [rbp+57h+var_68], rcx
0x18011905f  lea     rcx, aStatus_0; "Status"
0x180119066  mov     [rbp+57h+var_58], rcx
0x18011906a  lea     rcx, [rbp+57h+var_40]
0x18011906e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180119073  mov     rcx, [rbp+57h+var_48]
0x180119077  mov     ebx, eax
0x180119079  test    rcx, rcx
0x18011907c  jz      short loc_18011908E
0x18011907e  call    cs:__imp_BcdCloseObject
0x180119085  nop     dword ptr [rax+rax+00h]
0x18011908a  mov     [rbp+57h+var_48], r14
0x18011908e  mov     rcx, [rbp+57h+var_38]; void *
0x180119092  test    rcx, rcx
0x180119095  jz      short loc_18011909C
0x180119097  call    ?CloseBcdStore@@YAXPEAX@Z; CloseBcdStore(void *)
0x18011909c  mov     eax, ebx
0x18011909e  jmp     loc_1801192E7
0x1801190a3  lea     rcx, [rbp+57h+var_48]
0x1801190a7  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801190ac  mov     rcx, [rbp+57h+var_38]
0x1801190b0  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x1801190b7  mov     r8, rax
0x1801190ba  call    cs:__imp_BcdOpenObject
0x1801190c1  nop     dword ptr [rax+rax+00h]
0x1801190c6  test    eax, eax
0x1801190c8  jns     short loc_1801190D7
0x1801190ca  mov     [rbp+57h+var_60], 0F4h
0x1801190d2  jmp     loc_180119042
0x1801190d7  mov     rcx, [rbp+57h+var_48]
0x1801190db  lea     rax, [rbp+57h+Size]
0x1801190df  mov     edi, 14000008h
0x1801190e4  mov     [rsp+0A0h+var_80], rax
0x1801190e9  mov     edx, edi
0x1801190eb  xor     r9d, r9d
0x1801190ee  xor     r8d, r8d
0x1801190f1  call    cs:__imp_BcdGetElementDataWithFlags
0x1801190f8  nop     dword ptr [rax+rax+00h]
0x1801190fd  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180119101  cmp     r8, 10h
0x180119105  jb      loc_1801193DF
0x18011910b  mov     rcx, gs:60h
0x180119114  xor     edx, edx; Flags
0x180119116  mov     rcx, [rcx+30h]; HeapHandle
0x18011911a  call    cs:__imp_RtlAllocateHeap
0x180119121  nop     dword ptr [rax+rax+00h]
0x180119126  mov     rbx, rax
0x180119129  test    rax, rax
0x18011912c  jnz     short loc_180119169
0x18011912e  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180119135  mov     [rbp+57h+var_60], 0FEh
0x18011913d  mov     [rbp+57h+var_70], rcx
0x180119141  lea     rax, aRecoveryguidsA; "RecoveryGuids.AllocateBytes(BufferSize)"
0x180119148  lea     rcx, aGetwinreguid; "GetWinReGuid"
0x18011914f  mov     [rbp+57h+var_58], rax
0x180119153  mov     [rbp+57h+var_68], rcx
0x180119157  lea     rdx, [rbp+57h+var_70]
0x18011915b  lea     rcx, [rbp+57h+var_40]
0x18011915f  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180119164  jmp     loc_180119073
0x180119169  mov     rcx, [rbp+57h+var_48]
0x18011916d  lea     r9, [rbp+57h+Size]
0x180119171  mov     r8, rbx
0x180119174  mov     edx, edi
0x180119176  call    cs:__imp_BcdGetElementData
0x18011917d  nop     dword ptr [rax+rax+00h]
0x180119182  test    eax, eax
0x180119184  jns     short loc_1801191B7
0x180119186  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x18011918d  mov     [rbp+57h+var_60], 106h
0x180119195  mov     [rbp+57h+var_70], rcx
0x180119199  mov     r8d, eax
0x18011919c  lea     rcx, aGetwinreguid; "GetWinReGuid"
0x1801191a3  mov     [rbp+57h+var_68], rcx
0x1801191a7  lea     rcx, aStatus_0; "Status"
0x1801191ae  mov     [rbp+57h+var_58], rcx
0x1801191b2  jmp     loc_180119288
0x1801191b7  test    dword ptr [rbp+57h+Size], 0FFFFFFF0h
0x1801191be  mov     edi, r14d
0x1801191c1  jbe     loc_180119260
0x1801191c7  mov     eax, edi
0x1801191c9  lea     rcx, [rbp+57h+var_30]
0x1801191cd  add     rax, rax
0x1801191d0  mov     [rbp+57h+var_30], r14
0x1801191d4  movups  xmm0, xmmword ptr [rbx+rax*8]
0x1801191d8  movdqu  [rbp+57h+var_28], xmm0
0x1801191dd  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801191e2  mov     rcx, [rbp+57h+var_38]
0x1801191e6  lea     rdx, [rbp+57h+var_28]
0x1801191ea  mov     r8, rax
0x1801191ed  call    cs:__imp_BcdOpenObject
0x1801191f4  nop     dword ptr [rax+rax+00h]
0x1801191f9  test    eax, eax
0x1801191fb  js      loc_180119382
0x180119201  mov     rcx, [rbp+57h+var_30]
0x180119205  lea     r9, [rbp+57h+Size]
0x180119209  lea     r8, [rbp+57h+var_3C]
0x18011920d  mov     dword ptr [rbp+57h+Size], 2
0x180119214  mov     edx, 46000010h
0x180119219  call    cs:__imp_BcdGetElementData
0x180119220  nop     dword ptr [rax+rax+00h]
0x180119225  mov     edx, dword ptr [rbp+57h+Size]
0x180119228  test    eax, eax
0x18011922a  js      short loc_18011923B
0x18011922c  cmp     edx, 2
0x18011922f  jnz     short loc_18011923B
0x180119231  cmp     byte ptr [rbp+57h+var_3C], r14b
0x180119235  jnz     loc_18011930C
0x18011923b  mov     rcx, [rbp+57h+var_30]
0x18011923f  test    rcx, rcx
0x180119242  jz      short loc_180119253
0x180119244  call    cs:__imp_BcdCloseObject
0x18011924b  nop     dword ptr [rax+rax+00h]
0x180119250  mov     edx, dword ptr [rbp+57h+Size]
0x180119253  inc     edi
0x180119255  shr     edx, 4
0x180119258  cmp     edi, edx
0x18011925a  jb      loc_1801191C7
0x180119260  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180119267  mov     [rbp+57h+var_60], 128h
0x18011926f  mov     [rbp+57h+var_70], rcx
0x180119273  mov     r8d, 0C000000Fh
0x180119279  lea     rcx, aGetwinreguid; "GetWinReGuid"
0x180119280  mov     [rbp+57h+var_58], r14
0x180119284  mov     [rbp+57h+var_68], rcx
0x180119288  lea     rdx, [rbp+57h+var_70]
0x18011928c  lea     rcx, [rbp+57h+var_40]
0x180119290  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180119295  mov     edi, eax
0x180119297  mov     rcx, gs:60h
0x1801192a0  mov     r8, rbx; P
0x1801192a3  xor     edx, edx; Flags
0x1801192a5  mov     rcx, [rcx+30h]; HeapHandle
0x1801192a9  call    cs:__imp_RtlFreeHeap
0x1801192b0  nop     dword ptr [rax+rax+00h]
0x1801192b5  test    eax, eax
0x1801192b7  jnz     short loc_1801192BE
0x1801192b9  lea     ecx, [rax+7]
0x1801192bc  int     29h; Win8: RtlFailFast(ecx)
0x1801192be  mov     rcx, [rbp+57h+var_48]
0x1801192c2  test    rcx, rcx
0x1801192c5  jz      short loc_1801192D7
0x1801192c7  call    cs:__imp_BcdCloseObject
0x1801192ce  nop     dword ptr [rax+rax+00h]
0x1801192d3  mov     [rbp+57h+var_48], r14
0x1801192d7  mov     rcx, [rbp+57h+var_38]; void *
0x1801192db  test    rcx, rcx
0x1801192de  jz      short loc_1801192E5
0x1801192e0  call    ?CloseBcdStore@@YAXPEAX@Z; CloseBcdStore(void *)
0x1801192e5  mov     eax, edi
0x1801192e7  mov     rcx, [rbp+57h+var_18]
0x1801192eb  xor     rcx, rsp; StackCookie
0x1801192ee  call    __security_check_cookie
0x1801192f3  lea     r11, [rsp+0A0h+var_10]
0x1801192fb  mov     rbx, [r11+20h]
0x1801192ff  mov     rsi, [r11+30h]
0x180119303  mov     rsp, r11
0x180119306  pop     r14
0x180119308  pop     rdi
0x180119309  pop     rbp
0x18011930a  retn
0x18011930c  movups  xmm0, [rbp+57h+var_28]
0x180119310  mov     rcx, [rbp+57h+var_30]
0x180119314  movdqu  xmmword ptr [rsi], xmm0
0x180119318  test    rcx, rcx
0x18011931b  jz      short loc_18011932D
0x18011931d  call    cs:__imp_BcdCloseObject
0x180119324  nop     dword ptr [rax+rax+00h]
0x180119329  mov     [rbp+57h+var_30], r14
0x18011932d  mov     rcx, gs:60h
0x180119336  mov     r8, rbx; P
0x180119339  xor     edx, edx; Flags
0x18011933b  mov     rcx, [rcx+30h]; HeapHandle
0x18011933f  call    cs:__imp_RtlFreeHeap
0x180119346  nop     dword ptr [rax+rax+00h]
0x18011934b  test    eax, eax
0x18011934d  jnz     short loc_180119354
0x18011934f  lea     ecx, [rax+7]
0x180119352  int     29h; Win8: RtlFailFast(ecx)
0x180119354  mov     rcx, [rbp+57h+var_48]
0x180119358  test    rcx, rcx
0x18011935b  jz      short loc_18011936D
0x18011935d  call    cs:__imp_BcdCloseObject
0x180119364  nop     dword ptr [rax+rax+00h]
0x180119369  mov     [rbp+57h+var_48], r14
0x18011936d  mov     rcx, [rbp+57h+var_38]; void *
0x180119371  test    rcx, rcx
0x180119374  jz      short loc_18011937B
0x180119376  call    ?CloseBcdStore@@YAXPEAX@Z; CloseBcdStore(void *)
0x18011937b  xor     eax, eax
0x18011937d  jmp     loc_1801192E7
0x180119382  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180119389  mov     [rbp+57h+var_60], 113h
0x180119391  mov     [rbp+57h+var_70], rcx
0x180119395  lea     rdx, [rbp+57h+var_70]
0x180119399  lea     rcx, aGetwinreguid; "GetWinReGuid"
0x1801193a0  mov     r8d, eax
0x1801193a3  mov     [rbp+57h+var_68], rcx
0x1801193a7  lea     rcx, aStatus_0; "Status"
0x1801193ae  mov     [rbp+57h+var_58], rcx
0x1801193b2  lea     rcx, [rbp+57h+var_40]
0x1801193b6  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801193bb  mov     rcx, [rbp+57h+var_30]
0x1801193bf  mov     edi, eax
0x1801193c1  test    rcx, rcx
0x1801193c4  jz      loc_180119297
0x1801193ca  call    cs:__imp_BcdCloseObject
0x1801193d1  nop     dword ptr [rax+rax+00h]
0x1801193d6  mov     [rbp+57h+var_30], r14
0x1801193da  jmp     loc_180119297
0x1801193df  mov     ecx, 0C00000E5h; int
0x1801193e4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
