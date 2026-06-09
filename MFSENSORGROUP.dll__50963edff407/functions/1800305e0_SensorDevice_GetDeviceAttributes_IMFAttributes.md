# SensorDevice::GetDeviceAttributes(IMFAttributes * *)

- ea: `0x1800305e0`
- end: `0x180030771`
- name: `?GetDeviceAttributes@SensorDevice@@UEAAJPEAPEAUIMFAttributes@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(SensorDevice *__hidden this, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005fa0`
- `0x1800305e0`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030663`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030663`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800305f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800305f7`
- `MFPlat!MFCreateAttributes` at `0x18003067f`
- `MFPlat!MFCreateAttributes` at `0x18003067f`

## pseudocode

```c
__int64 __fastcall SensorDevice::GetDeviceAttributes(SensorDevice *this, struct IMFAttributes **a2)
{
  _QWORD *v4; // r14
  __int64 v5; // rcx
  UINT32 v6; // edx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  UINT32 cInitialSize; // [rsp+70h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !*((_QWORD *)this + 9) )
  {
    v8 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_7;
    v12 = 89;
LABEL_18:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
      (char *)this - 8,
      v8);
    goto LABEL_7;
  }
  if ( !a2 )
  {
    v8 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_7;
    v12 = 90;
    goto LABEL_18;
  }
  v4 = (_QWORD *)((char *)this + 96);
  *a2 = 0;
  if ( !*((_QWORD *)this + 12) )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = 1;
    cInitialSize = 1;
    if ( v5 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v5 + 240LL))(v5, &cInitialSize);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_7;
        v11 = 91;
LABEL_14:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
          (char *)this - 8,
          v7);
        goto LABEL_7;
      }
      v6 = cInitialSize;
    }
    v7 = MFCreateAttributes((IMFAttributes **)this + 12, v6);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_7;
      v11 = 92;
      goto LABEL_14;
    }
    v10 = *((_QWORD *)this + 11);
    if ( v10 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 256LL))(v10, *v4);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_7;
        v11 = 93;
        goto LABEL_14;
      }
    }
  }
  v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IMFAttributes **))*v4)(
         *v4,
         &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
         a2);
  v8 = v7;
  if ( v7 < 0 && g_wppLevels )
  {
    v11 = 94;
    goto LABEL_14;
  }
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v8;
}

```

## disassembly

```asm
0x1800305e0  push    rbx
0x1800305e2  push    rbp
0x1800305e3  push    rsi
0x1800305e4  push    rdi
0x1800305e5  push    r14
0x1800305e7  push    r15
0x1800305e9  sub     rsp, 38h
0x1800305ed  mov     rsi, rcx
0x1800305f0  mov     r15, rdx
0x1800305f3  add     rcx, 18h; lpCriticalSection
0x1800305f7  call    cs:__imp_EnterCriticalSection
0x1800305fd  lea     rdi, [rsi-8]
0x180030601  cmp     qword ptr [rdi+50h], 0
0x180030606  jz      loc_1800306EB
0x18003060c  test    r15, r15
0x18003060f  jz      loc_18003070F
0x180030615  lea     r14, [rsi+60h]
0x180030619  mov     qword ptr [r15], 0
0x180030620  cmp     qword ptr [r14], 0
0x180030624  jnz     short loc_18003069C
0x180030626  mov     rcx, [rsi+58h]
0x18003062a  mov     edx, 1
0x18003062f  mov     [rsp+68h+cInitialSize], edx
0x180030633  test    rcx, rcx
0x180030636  jz      short loc_18003067C
0x180030638  mov     rax, [rcx]
0x18003063b  lea     rdx, [rsp+68h+cInitialSize]
0x180030640  mov     rax, [rax+0F0h]
0x180030647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003064c  mov     ebx, eax
0x18003064e  test    eax, eax
0x180030650  jns     short loc_180030678
0x180030652  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030659  jnb     loc_180030723
0x18003065f  lea     rcx, [rsi+18h]; lpCriticalSection
0x180030663  call    cs:__imp_LeaveCriticalSection
0x180030669  mov     eax, ebx
0x18003066b  add     rsp, 38h
0x18003066f  pop     r15
0x180030671  pop     r14
0x180030673  pop     rdi
0x180030674  pop     rsi
0x180030675  pop     rbp
0x180030676  pop     rbx
0x180030677  retn
0x180030678  mov     edx, [rsp+68h+cInitialSize]; cInitialSize
0x18003067c  mov     rcx, r14; ppMFAttributes
0x18003067f  call    cs:__imp_MFCreateAttributes
0x180030685  mov     ebx, eax
0x180030687  test    eax, eax
0x180030689  js      loc_18003072A
0x18003068f  mov     rcx, [rsi+58h]
0x180030693  test    rcx, rcx
0x180030696  jnz     loc_18003073E
0x18003069c  mov     rcx, [r14]
0x18003069f  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800306a6  mov     r8, r15
0x1800306a9  mov     rax, [rcx]
0x1800306ac  mov     rax, [rax]
0x1800306af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306b4  mov     ebx, eax
0x1800306b6  test    eax, eax
0x1800306b8  jns     short loc_18003065F
0x1800306ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800306c1  jb      short loc_18003065F
0x1800306c3  mov     edx, 5Eh ; '^'
0x1800306c8  mov     [rsp+68h+var_48], eax
0x1800306cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306d3  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x1800306da  mov     r9, rdi
0x1800306dd  mov     rcx, [rcx+10h]
0x1800306e1  call    WPP_SF_qD
0x1800306e6  jmp     loc_18003065F
0x1800306eb  mov     ebx, 0C00D36B6h
0x1800306f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800306f7  jb      loc_18003065F
0x1800306fd  mov     edx, 59h ; 'Y'
0x180030702  jmp     short loc_180030709
0x180030704  mov     edx, 5Ah ; 'Z'
0x180030709  mov     [rsp+68h+var_48], ebx
0x18003070d  jmp     short loc_1800306CC
0x18003070f  mov     ebx, 80004003h
0x180030714  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003071b  jb      loc_18003065F
0x180030721  jmp     short loc_180030704
0x180030723  mov     edx, 5Bh ; '['
0x180030728  jmp     short loc_1800306C8
0x18003072a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030731  jb      loc_18003065F
0x180030737  mov     edx, 5Ch ; '\'
0x18003073c  jmp     short loc_1800306C8
0x18003073e  mov     rax, [rcx]
0x180030741  mov     rdx, [r14]
0x180030744  mov     rax, [rax+100h]
0x18003074b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030750  mov     ebx, eax
0x180030752  test    eax, eax
0x180030754  jns     loc_18003069C
0x18003075a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030761  jb      loc_18003065F
0x180030767  mov     edx, 5Dh ; ']'
0x18003076c  jmp     loc_1800306C8
```
