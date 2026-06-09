# EvtOpenPublisherEnum

- ea: `0x18001ef80`
- end: `0x18001f161`
- name: `EvtOpenPublisherEnum`
- size: `481`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, DWORD Flags)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x18000cf54`
- `0x18001ef80`
- `0x180023548`
- `0x180025bc4`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f111`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f111`
- `RPCRT4!NdrClientCall3` at `0x18001f08d`
- `RPCRT4!NdrClientCall3` at `0x18001f08d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
EVT_HANDLE __stdcall EvtOpenPublisherEnum(EVT_HANDLE Session, DWORD Flags)
{
  CLIENT_CALL_RETURN v3; // rcx
  DWORD Pointer; // ebx
  wchar_t **v5; // r14
  unsigned int v6; // r15d
  __int64 v7; // rax
  void *v8; // rbx
  wmi::RefBase *v10; // [rsp+40h] [rbp-78h] BYREF
  int v11; // [rsp+4Ch] [rbp-6Ch]
  EvtException *v12[2]; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v13; // [rsp+60h] [rbp-58h]
  int v14; // [rsp+64h] [rbp-54h]
  char v15; // [rsp+68h] [rbp-50h]
  __int128 pExceptionObject; // [rsp+70h] [rbp-48h] BYREF
  __int64 v17; // [rsp+80h] [rbp-38h]
  int v18; // [rsp+88h] [rbp-30h]
  int v19; // [rsp+8Ch] [rbp-2Ch]
  int v20; // [rsp+90h] [rbp-28h]
  unsigned int v21; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v22; // [rsp+D0h] [rbp+18h] BYREF
  wchar_t **v23; // [rsp+D8h] [rbp+20h] BYREF

  v22 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v17 = 0;
      v18 = 87;
      v19 = -1;
      v20 = 1615;
      throw (EvtException *)&pExceptionObject;
    }
    GetSession(&v10);
    v23 = 0;
    v21 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x16u,
                              0,
                              *((_QWORD *)v10 + 9),
                              0,
                              &v21,
                              &v23).Pointer;
    v5 = v23;
    v6 = v21;
    v12[1] = (EvtException *)v23;
    v13 = v21;
    v14 = v11;
    v15 = 1;
    if ( !Pointer )
      Pointer = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ObjectTable::EmplaceObject<PublisherEnumObject,wchar_t * * &,unsigned long &>)(
                  (CLIENT_CALL_RETURN)v3.Simple,
                  &v22,
                  &v23,
                  &v21);
    CleanupStringVector(v6, v5);
    if ( v10 )
      wmi::RefBase::Release(v10);
  }
  catch ( EvtException *v12 )
  {
    v21 = *((_DWORD *)v12[0] + 6);
    Pointer = v21;
  }
  SetLastError(Pointer);
  v7 = v22;
  if ( v22 )
  {
    v8 = *(void **)(v22 + 16);
    v22 = 0;
    *(_BYTE *)(v7 + 29) = 1;
  }
  else
  {
    v8 = 0;
  }
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v22);
  return v8;
}

```

## disassembly

```asm
0x18001ef80  mov     rax, rsp
0x18001ef83  mov     [rax+8], rbx
0x18001ef87  push    rsi
0x18001ef88  push    r14
0x18001ef8a  push    r15
0x18001ef8c  sub     rsp, 0A0h
0x18001ef93  mov     ebx, edx
0x18001ef95  mov     rsi, rcx
0x18001ef98  mov     qword ptr [rax+18h], 0
0x18001efa0  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18001efa5  test    ebx, ebx
0x18001efa7  jz      loc_18001F02F
0x18001efad  lea     rax, WPP_GLOBAL_Control
0x18001efb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efbb  cmp     rcx, rax
0x18001efbe  jz      short loc_18001EFE8
0x18001efc0  mov     esi, 1
0x18001efc5  test    [rcx+1Ch], sil
0x18001efc9  jz      short loc_18001EFE8
0x18001efcb  cmp     byte ptr [rcx+19h], 2
0x18001efcf  jb      short loc_18001EFE8
0x18001efd1  lea     edx, [rsi+30h]
0x18001efd4  lea     r9d, [rsi+56h]
0x18001efd8  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001efdf  mov     rcx, [rcx+10h]
0x18001efe3  call    WPP_SF_D
0x18001efe8  xorps   xmm0, xmm0
0x18001efeb  movdqu  [rsp+0B8h+pExceptionObject], xmm0
0x18001eff1  mov     [rsp+0B8h+var_38], 0
0x18001effd  mov     [rsp+0B8h+var_30], 57h ; 'W'
0x18001f008  mov     [rsp+0B8h+var_2C], 0FFFFFFFFh
0x18001f013  mov     [rsp+0B8h+var_28], 64Fh
0x18001f01e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f025  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18001f02a  call    _CxxThrowException_0
0x18001f02f  mov     rdx, rsi
0x18001f032  lea     rcx, [rsp+0B8h+var_78]; void *
0x18001f037  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18001f03c  nop
0x18001f03d  mov     [rsp+0B8h+arg_18], 0
0x18001f049  mov     [rsp+0B8h+arg_8], 0
0x18001f054  lea     rax, [rsp+0B8h+arg_18]
0x18001f05c  mov     [rsp+0B8h+var_88], rax
0x18001f061  lea     rax, [rsp+0B8h+arg_8]
0x18001f069  mov     [rsp+0B8h+var_90], rax
0x18001f06e  mov     [rsp+0B8h+var_98], 0
0x18001f076  mov     r9, [rsp+0B8h+var_78]
0x18001f07b  mov     r9, [r9+48h]
0x18001f07f  xor     r8d, r8d; pReturnValue
0x18001f082  lea     edx, [r8+16h]; nProcNum
0x18001f086  lea     rcx, pProxyInfo; pProxyInfo
0x18001f08d  call    cs:__imp_NdrClientCall3
0x18001f093  mov     rbx, rax
0x18001f096  mov     r14, [rsp+0B8h+arg_18]
0x18001f09e  mov     r15d, [rsp+0B8h+arg_8]
0x18001f0a6  mov     [rsp+0B8h+var_60], r14
0x18001f0ab  mov     [rsp+0B8h+var_58], r15d
0x18001f0b0  mov     eax, [rsp+0B8h+var_6C]
0x18001f0b4  mov     [rsp+0B8h+var_54], eax
0x18001f0b8  mov     esi, 1
0x18001f0bd  mov     [rsp+0B8h+var_50], sil
0x18001f0c2  test    ebx, ebx
0x18001f0c4  jnz     short loc_18001F0E5
0x18001f0c6  lea     r9, [rsp+0B8h+arg_8]
0x18001f0ce  lea     r8, [rsp+0B8h+arg_18]
0x18001f0d6  lea     rdx, [rsp+0B8h+arg_10]
0x18001f0de  call    ??$EmplaceObject@VPublisherEnumObject@@AEAPEAPEA_WAEAK@ObjectTable@@QEAAKAEAVEvtHandleRef@@AEAPEAPEA_WAEAK@Z; ObjectTable::EmplaceObject<PublisherEnumObject,wchar_t * * &,ulong &>(EvtHandleRef &,wchar_t * * &,ulong &)
0x18001f0e3  mov     ebx, eax
0x18001f0e5  mov     rdx, r14; wchar_t **
0x18001f0e8  mov     ecx, r15d; unsigned int
0x18001f0eb  call    ?CleanupStringVector@@YAXKPEAPEA_W@Z; CleanupStringVector(ulong,wchar_t * *)
0x18001f0f0  nop
0x18001f0f1  mov     rcx, [rsp+0B8h+var_78]; this
0x18001f0f6  test    rcx, rcx
0x18001f0f9  jz      short loc_18001F101
0x18001f0fb  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001f100  nop
0x18001f101  jmp     short loc_18001F10F
0x18001f103  mov     esi, 1
0x18001f108  mov     ebx, [rsp+0B8h+arg_8]
0x18001f10f  mov     ecx, ebx; dwErrCode
0x18001f111  call    cs:__imp_SetLastError
0x18001f117  mov     rax, [rsp+0B8h+arg_10]
0x18001f11f  test    rax, rax
0x18001f122  jz      short loc_18001F13A
0x18001f124  mov     rbx, [rax+10h]
0x18001f128  mov     [rsp+0B8h+arg_10], 0
0x18001f134  xchg    sil, [rax+1Dh]
0x18001f138  jmp     short loc_18001F13C
0x18001f13a  xor     ebx, ebx
0x18001f13c  lea     rcx, [rsp+0B8h+arg_10]; this
0x18001f144  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001f149  mov     rax, rbx
0x18001f14c  mov     rbx, [rsp+0B8h+arg_0]
0x18001f154  add     rsp, 0A0h
0x18001f15b  pop     r15
0x18001f15d  pop     r14
0x18001f15f  pop     rsi
0x18001f160  retn
```
