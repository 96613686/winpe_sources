# SensorGroup::GetSensorGroupAttributes(IMFAttributes * *)

- ea: `0x180030450`
- end: `0x1800305ce`
- name: `?GetSensorGroupAttributes@SensorGroup@@UEAAJPEAPEAUIMFAttributes@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005fa0`
- `0x180030450`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030520`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030520`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003046c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003046c`
- `MFPlat!MFCreateAttributes` at `0x1800304c9`
- `MFPlat!MFCreateAttributes` at `0x1800304c9`

## pseudocode

```c
__int64 __fastcall SensorGroup::GetSensorGroupAttributes(SensorGroup *this, struct IMFAttributes **a2)
{
  UINT32 v4; // edx
  __int64 v5; // rcx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rsi
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  UINT32 cInitialSize; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v4 = 0;
  cInitialSize = 0;
  if ( !*((_QWORD *)this + 22) )
  {
    v7 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_11;
    v11 = 24;
    goto LABEL_14;
  }
  if ( !a2 )
  {
    v7 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_11;
    v11 = 25;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v7);
    goto LABEL_11;
  }
  *a2 = 0;
  v5 = *((_QWORD *)this + 9);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v5 + 240LL))(v5, &cInitialSize);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_11;
      v12 = 26;
LABEL_25:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v6);
      goto LABEL_11;
    }
    v4 = cInitialSize;
  }
  v8 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
    goto LABEL_10;
  v6 = MFCreateAttributes((IMFAttributes **)this + 10, v4);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_11;
    v12 = 27;
    goto LABEL_25;
  }
  v9 = *((_QWORD *)this + 9);
  if ( v9 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 256LL))(v9, *v8);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_11;
      v12 = 28;
      goto LABEL_25;
    }
  }
LABEL_10:
  v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IMFAttributes **))*v8)(
         *v8,
         &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
         a2);
  v7 = v6;
  if ( v6 < 0 && g_wppLevels )
  {
    v12 = 29;
    goto LABEL_25;
  }
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return v7;
}

```

## disassembly

```asm
0x180030450  mov     [rsp+arg_8], rbx
0x180030455  mov     [rsp+arg_10], rbp
0x18003045a  push    rsi
0x18003045b  push    rdi
0x18003045c  push    r14
0x18003045e  sub     rsp, 30h
0x180030462  mov     rdi, rcx
0x180030465  mov     r14, rdx
0x180030468  add     rcx, 20h ; ' '; lpCriticalSection
0x18003046c  call    cs:__imp_EnterCriticalSection
0x180030472  xor     edx, edx
0x180030474  mov     [rsp+48h+cInitialSize], edx
0x180030478  cmp     [rdi+0B0h], rdx
0x18003047f  jz      loc_180030554
0x180030485  test    r14, r14
0x180030488  jz      loc_18003053B
0x18003048e  mov     [r14], rdx
0x180030491  mov     rcx, [rdi+48h]
0x180030495  test    rcx, rcx
0x180030498  jz      short loc_1800304BC
0x18003049a  mov     rax, [rcx]
0x18003049d  lea     rdx, [rsp+48h+cInitialSize]
0x1800304a2  mov     rax, [rax+0F0h]
0x1800304a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304ae  mov     ebx, eax
0x1800304b0  test    eax, eax
0x1800304b2  js      loc_180030569
0x1800304b8  mov     edx, [rsp+48h+cInitialSize]; cInitialSize
0x1800304bc  lea     rsi, [rdi+50h]
0x1800304c0  cmp     qword ptr [rsi], 0
0x1800304c4  jnz     short loc_1800304FE
0x1800304c6  mov     rcx, rsi; ppMFAttributes
0x1800304c9  call    cs:__imp_MFCreateAttributes
0x1800304cf  mov     ebx, eax
0x1800304d1  test    eax, eax
0x1800304d3  js      loc_180030579
0x1800304d9  mov     rcx, [rdi+48h]
0x1800304dd  test    rcx, rcx
0x1800304e0  jz      short loc_1800304FE
0x1800304e2  mov     rax, [rcx]
0x1800304e5  mov     rdx, [rsi]
0x1800304e8  mov     rax, [rax+100h]
0x1800304ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304f4  mov     ebx, eax
0x1800304f6  test    eax, eax
0x1800304f8  js      loc_180030589
0x1800304fe  mov     rcx, [rsi]
0x180030501  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x180030508  mov     r8, r14
0x18003050b  mov     rax, [rcx]
0x18003050e  mov     rax, [rax]
0x180030511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030516  mov     ebx, eax
0x180030518  test    eax, eax
0x18003051a  js      short loc_180030599
0x18003051c  lea     rcx, [rdi+20h]; lpCriticalSection
0x180030520  call    cs:__imp_LeaveCriticalSection
0x180030526  mov     rbp, [rsp+48h+arg_10]
0x18003052b  mov     eax, ebx
0x18003052d  mov     rbx, [rsp+48h+arg_8]
0x180030532  add     rsp, 30h
0x180030536  pop     r14
0x180030538  pop     rdi
0x180030539  pop     rsi
0x18003053a  retn
0x18003053b  mov     ebx, 80004003h
0x180030540  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030547  jb      short loc_18003051C
0x180030549  mov     edx, 19h
0x18003054e  mov     [rsp+48h+var_28], ebx
0x180030552  jmp     short loc_1800305AF
0x180030554  mov     ebx, 0C00D36B6h
0x180030559  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030560  jb      short loc_18003051C
0x180030562  mov     edx, 18h
0x180030567  jmp     short loc_18003054E
0x180030569  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030570  jb      short loc_18003051C
0x180030572  mov     edx, 1Ah
0x180030577  jmp     short loc_1800305AB
0x180030579  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030580  jb      short loc_18003051C
0x180030582  mov     edx, 1Bh
0x180030587  jmp     short loc_1800305AB
0x180030589  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030590  jb      short loc_18003051C
0x180030592  mov     edx, 1Ch
0x180030597  jmp     short loc_1800305AB
0x180030599  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800305a0  jb      loc_18003051C
0x1800305a6  mov     edx, 1Dh
0x1800305ab  mov     [rsp+48h+var_28], eax
0x1800305af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305b6  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x1800305bd  mov     r9, rdi
0x1800305c0  mov     rcx, [rcx+10h]
0x1800305c4  call    WPP_SF_qD
0x1800305c9  jmp     loc_18003051C
```
