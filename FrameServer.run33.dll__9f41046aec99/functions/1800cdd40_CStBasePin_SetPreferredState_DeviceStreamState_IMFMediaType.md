# CStBasePin::SetPreferredState(_DeviceStreamState,IMFMediaType *)

- ea: `0x1800cdd40`
- end: `0x1800cdfd4`
- name: `?SetPreferredState@CStBasePin@@UEAAJW4_DeviceStreamState@@PEAUIMFMediaType@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(CStBasePin *__hidden this, enum _DeviceStreamState, struct IMFMediaType *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800095c8`
- `0x180009608`
- `0x180017ccc`
- `0x180018e9c`
- `0x1800cc564`
- `0x1800cdd40`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdfb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdfb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cdd64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cdd64`
- `MFPlat!MFCreateMediaEvent` at `0x1800cde7d`
- `MFPlat!MFCreateMediaEvent` at `0x1800cde7d`

## pseudocode

```c
__int64 __fastcall CStBasePin::SetPreferredState(CStBasePin *this, enum _DeviceStreamState a2, struct IMFMediaType *a3)
{
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _BYTE *v10; // rdi
  int v11; // ecx
  HRESULT v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  IMFMediaEvent *v17; // rdi
  HRESULT (__stdcall *SetUINT32)(IMFMediaEvent *, const GUID *const, UINT32); // rbx
  unsigned int v19; // eax
  int v21; // [rsp+70h] [rbp+8h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+88h] [rbp+20h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v21 = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v8 = -1072861856;
    if ( !g_wppLevels )
      goto LABEL_31;
    v9 = 16;
    goto LABEL_4;
  }
  if ( !*((_QWORD *)this + 5) )
    Microsoft::WRL::ComPtr<IMFMediaType>::operator=((char *)this + 40, (char *)this + 32);
  if ( a3 )
  {
    v10 = (char *)this + 9;
    if ( (*(unsigned int (__fastcall **)(_QWORD, struct IMFMediaType *, int *))(**((_QWORD **)this + 5) + 280LL))(
           *((_QWORD *)this + 5),
           a3,
           &v21) )
    {
      *v10 = 1;
      goto LABEL_15;
    }
  }
  else
  {
    if ( a2 )
    {
      v8 = -2147024809;
      if ( g_wppLevels )
      {
        v9 = 17;
LABEL_4:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          &WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids,
          (char *)this - 80,
          v8);
        goto LABEL_31;
      }
      goto LABEL_31;
    }
    v10 = (char *)this + 9;
  }
  *v10 = 0;
LABEL_15:
  v11 = *((_DWORD *)this + 6);
  v8 = 0;
  *((_DWORD *)this + 7) = a2;
  *((_BYTE *)this + 8) = v11 != a2;
  if ( *v10 || v11 != a2 )
  {
    if ( *((_DWORD *)this + 4) != -1 )
    {
      ppEvent = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppEvent, 0, v6, v7);
      v12 = MFCreateMediaEvent(0x25Du, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
      v8 = v12;
      if ( v12 >= 0 )
      {
        v17 = ppEvent;
        SetUINT32 = ppEvent->lpVtbl->SetUINT32;
        v19 = (*(__int64 (__fastcall **)(CStBasePin *))(*(_QWORD *)this + 88LL))(this);
        v12 = ((__int64 (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))SetUINT32)(
                v17,
                &MF_EVENT_MFT_INPUT_STREAM_ID,
                v19);
        v8 = v12;
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaEvent *))(**((_QWORD **)this + 6) + 48LL))(
                  *((_QWORD *)this + 6),
                  ppEvent);
          v8 = v12;
          if ( v12 >= 0 || !g_wppLevels )
            goto LABEL_22;
          v16 = 20;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_22;
          v16 = 19;
        }
      }
      else
      {
        if ( !g_wppLevels )
        {
LABEL_22:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppEvent, v13, v14, v15);
          goto LABEL_31;
        }
        v16 = 18;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids,
        (char *)this - 80,
        v12);
      goto LABEL_22;
    }
    if ( (unsigned __int8)byte_18010EC4D < 8u )
      goto LABEL_33;
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      21,
      &WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids,
      (char *)this - 80);
  }
LABEL_31:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      22,
      &WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids,
      (char *)this - 80,
      a2,
      *((_DWORD *)this + 6),
      v8);
LABEL_33:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v8;
}

```

## disassembly

```asm
0x1800cdd40  mov     [rsp+arg_8], rbx
0x1800cdd45  mov     [rsp+arg_10], rsi
0x1800cdd4a  push    rdi
0x1800cdd4b  push    r12
0x1800cdd4d  push    r13
0x1800cdd4f  push    r14
0x1800cdd51  push    r15
0x1800cdd53  sub     rsp, 40h
0x1800cdd57  mov     rsi, rcx
0x1800cdd5a  mov     r12, r8
0x1800cdd5d  add     rcx, 40h ; '@'; lpCriticalSection
0x1800cdd61  mov     r15d, edx
0x1800cdd64  call    cs:__imp_EnterCriticalSection
0x1800cdd6a  xor     edx, edx
0x1800cdd6c  lea     r14, [rsi-50h]
0x1800cdd70  mov     [rsp+68h+arg_0], edx
0x1800cdd74  cmp     [r14+70h], rdx
0x1800cdd78  jnz     short loc_1800CDDB4
0x1800cdd7a  mov     ebx, 0C00D6D60h
0x1800cdd7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdd86  jb      loc_1800CDF73
0x1800cdd8c  mov     edx, 10h
0x1800cdd91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdd98  lea     r8, WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids
0x1800cdd9f  mov     r9, r14
0x1800cdda2  mov     dword ptr [rsp+68h+ppEvent], ebx
0x1800cdda6  mov     rcx, [rcx+10h]
0x1800cddaa  call    WPP_SF_qD
0x1800cddaf  jmp     loc_1800CDF73
0x1800cddb4  lea     rbx, [rsi+28h]
0x1800cddb8  cmp     [rbx], rdx
0x1800cddbb  jnz     short loc_1800CDDCB
0x1800cddbd  lea     rdx, [rsi+20h]
0x1800cddc1  mov     rcx, rbx
0x1800cddc4  call    ??4?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMFMediaType>::operator=(Microsoft::WRL::ComPtr<IMFMediaType> const &)
0x1800cddc9  xor     edx, edx
0x1800cddcb  test    r12, r12
0x1800cddce  jnz     short loc_1800CDDF4
0x1800cddd0  test    r15d, r15d
0x1800cddd3  jnz     short loc_1800CDDDB
0x1800cddd5  lea     rdi, [rsi+9]
0x1800cddd9  jmp     short loc_1800CDE18
0x1800cdddb  mov     ebx, 80070057h
0x1800cdde0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdde7  jb      loc_1800CDF73
0x1800cdded  mov     edx, 11h
0x1800cddf2  jmp     short loc_1800CDD91
0x1800cddf4  mov     rcx, [rbx]
0x1800cddf7  lea     r8, [rsp+68h+arg_0]
0x1800cddfc  mov     rdx, r12
0x1800cddff  lea     rdi, [rsi+9]
0x1800cde03  mov     rax, [rcx]
0x1800cde06  mov     rax, [rax+118h]
0x1800cde0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cde12  xor     edx, edx
0x1800cde14  test    eax, eax
0x1800cde16  jnz     short loc_1800CDE1C
0x1800cde18  mov     [rdi], dl
0x1800cde1a  jmp     short loc_1800CDE1F
0x1800cde1c  mov     byte ptr [rdi], 1
0x1800cde1f  mov     ecx, [rsi+18h]
0x1800cde22  mov     ebx, edx
0x1800cde24  cmp     ecx, r15d
0x1800cde27  mov     [rsi+1Ch], r15d
0x1800cde2b  setnz   al
0x1800cde2e  mov     [r14+58h], al
0x1800cde32  cmp     [rdi], dl
0x1800cde34  jnz     short loc_1800CDE3F
0x1800cde36  cmp     ecx, r15d
0x1800cde39  jz      loc_1800CDF73
0x1800cde3f  cmp     dword ptr [rsi+10h], 0FFFFFFFFh
0x1800cde43  jz      loc_1800CDF48
0x1800cde49  lea     rcx, [rsp+68h+arg_18]
0x1800cde51  mov     [rsp+68h+arg_18], rdx
0x1800cde59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cde5e  lea     rax, [rsp+68h+arg_18]
0x1800cde66  xor     r9d, r9d; pvValue
0x1800cde69  xor     r8d, r8d; hrStatus
0x1800cde6c  mov     [rsp+68h+ppEvent], rax; ppEvent
0x1800cde71  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x1800cde78  mov     ecx, 25Dh; met
0x1800cde7d  call    cs:__imp_MFCreateMediaEvent
0x1800cde83  mov     ebx, eax
0x1800cde85  test    eax, eax
0x1800cde87  jns     short loc_1800CDEC7
0x1800cde89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cde90  jb      short loc_1800CDEB5
0x1800cde92  mov     edx, 12h
0x1800cde97  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cde9e  lea     r8, WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids
0x1800cdea5  mov     r9, r14
0x1800cdea8  mov     dword ptr [rsp+68h+ppEvent], eax
0x1800cdeac  mov     rcx, [rcx+10h]
0x1800cdeb0  call    WPP_SF_qD
0x1800cdeb5  lea     rcx, [rsp+68h+arg_18]
0x1800cdebd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cdec2  jmp     loc_1800CDF73
0x1800cdec7  mov     rdi, [rsp+68h+arg_18]
0x1800cdecf  mov     rcx, rsi
0x1800cded2  mov     rdx, [rsi]
0x1800cded5  mov     rax, [rdi]
0x1800cded8  mov     rbx, [rax+0A8h]
0x1800cdedf  mov     rax, [rdx+58h]
0x1800cdee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdee8  mov     r8d, eax
0x1800cdeeb  lea     rdx, MF_EVENT_MFT_INPUT_STREAM_ID
0x1800cdef2  mov     rax, rbx
0x1800cdef5  mov     rcx, rdi
0x1800cdef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdefd  mov     ebx, eax
0x1800cdeff  test    eax, eax
0x1800cdf01  jns     short loc_1800CDF13
0x1800cdf03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdf0a  jb      short loc_1800CDEB5
0x1800cdf0c  mov     edx, 13h
0x1800cdf11  jmp     short loc_1800CDE97
0x1800cdf13  mov     rcx, [rsi+30h]
0x1800cdf17  mov     rdx, [rsp+68h+arg_18]
0x1800cdf1f  mov     rax, [rcx]
0x1800cdf22  mov     rax, [rax+30h]
0x1800cdf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdf2b  mov     ebx, eax
0x1800cdf2d  test    eax, eax
0x1800cdf2f  jns     short loc_1800CDEB5
0x1800cdf31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdf38  jb      loc_1800CDEB5
0x1800cdf3e  mov     edx, 14h
0x1800cdf43  jmp     loc_1800CDE97
0x1800cdf48  cmp     cs:byte_18010EC4D, 8
0x1800cdf4f  jb      short loc_1800CDFAE
0x1800cdf51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdf58  lea     r8, WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids
0x1800cdf5f  mov     edx, 15h
0x1800cdf64  mov     r9, r14
0x1800cdf67  mov     rcx, [rcx+0D8h]
0x1800cdf6e  call    WPP_SF_q
0x1800cdf73  cmp     cs:byte_18010EC4D, 8
0x1800cdf7a  jb      short loc_1800CDFAE
0x1800cdf7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdf83  lea     r8, WPP_10aa55c11b693a1ece5833cd9052c18c_Traceguids
0x1800cdf8a  mov     eax, [rsi+18h]
0x1800cdf8d  mov     edx, 16h
0x1800cdf92  mov     [rsp+68h+var_38], ebx
0x1800cdf96  mov     r9, r14
0x1800cdf99  mov     [rsp+68h+var_40], eax
0x1800cdf9d  mov     rcx, [rcx+0D8h]
0x1800cdfa4  mov     dword ptr [rsp+68h+ppEvent], r15d
0x1800cdfa9  call    WPP_SF_qddd
0x1800cdfae  lea     rcx, [rsi+40h]; lpCriticalSection
0x1800cdfb2  call    cs:__imp_LeaveCriticalSection
0x1800cdfb8  lea     r11, [rsp+68h+var_28]
0x1800cdfbd  mov     eax, ebx
0x1800cdfbf  mov     rbx, [r11+38h]
0x1800cdfc3  mov     rsi, [r11+40h]
0x1800cdfc7  mov     rsp, r11
0x1800cdfca  pop     r15
0x1800cdfcc  pop     r14
0x1800cdfce  pop     r13
0x1800cdfd0  pop     r12
0x1800cdfd2  pop     rdi
0x1800cdfd3  retn
```
