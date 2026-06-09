# waveInOpen

- ea: `0x1800048e0`
- end: `0x180004d90`
- name: `waveInOpen`
- size: `1200`
- prototype: `MMRESULT __stdcall(LPHWAVEIN phwi, UINT uDeviceID, LPCWAVEFORMATEX pwfx, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1800048e0`

## callees

- `0x180001564`
- `0x180004480`
- `0x180004534`
- `0x1800048e0`
- `0x1800065d0`
- `0x180007d70`
- `0x180007dd0`
- `0x18000aef0`
- `0x18000e0d0`
- `0x18000e828`
- `0x1800106c0`
- `0x18001d4d4`
- `0x18001d52c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d70`

## pseudocode

```c
MMRESULT __stdcall waveInOpen(
        LPHWAVEIN phwi,
        UINT uDeviceID,
        LPCWAVEFORMATEX pwfx,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  unsigned int v6; // r15d
  __int128 v8; // rdi
  UINT v9; // r14d
  DWORD v10; // r12d
  __int64 v11; // rcx
  struct HWAVEOUT__ *i; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  ULONGLONG v15; // rsi
  unsigned int v16; // edi
  struct _MMDRV *Ptr; // r15
  int v19; // eax
  UINT v20; // r15d
  struct _RTL_CRITICAL_SECTION *v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  __int64 v23; // rax
  DWORD v24; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-65h] BYREF
  DWORD v26; // [rsp+48h] [rbp-61h]
  LPHWAVEIN phwia; // [rsp+50h] [rbp-59h]
  DWORD_PTR dwCallbacka; // [rsp+58h] [rbp-51h]
  __int64 v29; // [rsp+60h] [rbp-49h] BYREF
  _OWORD v30[3]; // [rsp+68h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+98h] [rbp-11h] BYREF

  v6 = 0;
  phwia = phwi;
  v25 = 0;
  v31.Ptr = 0;
  dwCallbacka = dwCallback;
  *((_QWORD *)&v8 + 1) = pwfx;
  v29 = 0;
  *(_QWORD *)&v8 = phwi;
  memset(v30, 0, 44);
  if ( pwfx && (!dwCallback || (unsigned int)ValidateCallbackType(dwCallback, HIWORD(fdwOpen))) )
  {
    v9 = -1;
    if ( uDeviceID != 0xFFFF )
      v9 = uDeviceID;
    if ( v9 == -1 )
    {
      if ( (fdwOpen & 0x7E04) == 0 )
        goto LABEL_7;
    }
    else if ( (fdwOpen & 0x7E10) == 0 )
    {
LABEL_7:
      if ( **((_WORD **)&v8 + 1) == 1 || !*(_WORD *)(*((_QWORD *)&v8 + 1) + 16LL) || *((_QWORD *)&v8 + 1) != -18 )
      {
        v10 = fdwOpen & 1;
        v26 = v10;
        if ( (fdwOpen & 1) != 0 )
        {
          phwia = 0;
LABEL_10:
          ClientUpdatePnpInfo();
          if ( !wTotalWaveInDevs )
            goto LABEL_27;
          v24 = fdwOpen & 4;
          if ( (fdwOpen & 4) != 0 || v9 == -1 )
          {
            WaveMapperInit();
            EnterCriticalSection(&NumDevsCritSec);
            for ( i = *(struct HWAVEOUT__ **)&waveindrvZ.unused; i != &waveindrvZ; i = *(struct HWAVEOUT__ **)i )
            {
              if ( ((_BYTE)i[28] & 2) != 0 )
                goto LABEL_18;
            }
            goto LABEL_26;
          }
          EnterCriticalSection(&NumDevsCritSec);
          i = *(struct HWAVEOUT__ **)&waveindrvZ.unused;
          if ( *(struct HWAVEOUT__ **)&waveindrvZ.unused == &waveindrvZ )
            goto LABEL_26;
          v6 = v9;
          while ( 1 )
          {
            if ( ((_BYTE)i[28] & 2) == 0 )
            {
              v13 = *((_DWORD *)i + 22);
              if ( v13 > v6 )
              {
                if ( i != &waveindrvZ )
                {
LABEL_18:
                  _InterlockedIncrement((volatile signed __int32 *)i + 23);
                  v31.Ptr = (ULONGLONG)i;
                  v25 = v6;
                  LeaveCriticalSection(&NumDevsCritSec);
                  if ( v9 == -1 && !*((_QWORD *)i + 10) )
                  {
                    mregDecUsagePtr((struct _MMDRV *)i);
                    if ( v24 )
                    {
                      v24 = waveReferenceDriverById(&waveindrvZ, 0xFFFFFFFFLL, &v31, &v25);
                      v16 = v24;
                      if ( !v24 )
                      {
                        Ptr = (struct _MMDRV *)v31.Ptr;
                        v19 = mregHandleInternalMessages((struct _MMDRV *)v31.Ptr, 1, v25, 0x805u, 0, 0, (int *)&v24);
                        v16 = v24;
                        if ( !v19 && !v24 )
                          v16 = waveInOpen(
                                  phwia,
                                  0xFFFFFFFF,
                                  *((LPCWAVEFORMATEX *)&v8 + 1),
                                  dwCallbacka,
                                  dwInstance,
                                  fdwOpen & 0xFFFFFFFB);
                        mregDecUsagePtr(Ptr);
                      }
                    }
                    else
                    {
                      v20 = 0;
                      v16 = 4;
                      if ( wTotalWaveInDevs )
                      {
                        do
                        {
                          v16 = waveInOpen(phwia, v20, *((LPCWAVEFORMATEX *)&v8 + 1), dwCallbacka, dwInstance, fdwOpen);
                          if ( !v16 )
                            break;
                          ++v20;
                        }
                        while ( v20 < wTotalWaveInDevs );
                        v10 = v26;
                      }
                    }
                    goto LABEL_28;
                  }
                  if ( (fdwOpen & 1) != 0 )
                  {
                    *(_QWORD *)&v8 = 0;
                    v31.Ptr = 0;
LABEL_21:
                    *(_QWORD *)&v30[1] = dwCallbacka;
                    *((_QWORD *)&v30[1] + 1) = dwInstance;
                    v30[0] = v8;
                    LODWORD(v30[2]) = v9;
                    *(_QWORD *)((char *)&v30[2] + 4) = *((_QWORD *)i + 13);
                    v14 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64 *, _OWORD *, _QWORD))i + 10))(
                            v6,
                            52,
                            &v29,
                            v30,
                            fdwOpen);
                    v15 = v31.Ptr;
                    v16 = v14;
                    if ( v31.Ptr )
                    {
                      v22 = (struct _RTL_CRITICAL_SECTION *)(v31.Ptr - 40);
                      if ( v14 )
                      {
                        LeaveCriticalSection(v22);
                        FreeHandle(v15);
                      }
                      else
                      {
                        *(_DWORD *)(v31.Ptr - 68) &= ~2u;
                        LeaveCriticalSection(v22);
                        _InterlockedIncrement((volatile signed __int32 *)i + 23);
                        v23 = v29;
                        *phwia = (HWAVEIN)v15;
                        *(_QWORD *)(v15 + 16) = v23;
                      }
                    }
                    EnterCriticalSection(&NumDevsCritSec);
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)i + 23, 0xFFFFFFFF) == 1 )
                      mregRemoveDriver((struct _MMDRV *)i);
                    LeaveCriticalSection(&NumDevsCritSec);
LABEL_28:
                    if ( v10 )
                      return v16;
                  }
                  else
                  {
                    v21 = NewHandle(2, *((_QWORD *)i + 12), 0x20u);
                    v31.Ptr = (ULONGLONG)v21;
                    *(_QWORD *)&v8 = v21;
                    if ( v21 )
                    {
                      EnterCriticalSection(v21 - 1);
                      *(_DWORD *)(v8 - 68) |= 2u;
                      LeaveCriticalSection(&HandleListCritSec);
                      *(_QWORD *)v8 = i;
                      *(_DWORD *)(v8 + 8) = v6;
                      *(_DWORD *)(v8 + 24) = v9;
                      *(_DWORD *)(v8 + 28) = 0;
                      goto LABEL_21;
                    }
                    v16 = 7;
                  }
                  if ( (WinMMEnableBits & 1) != 0 )
                    McTemplateU0q_EventWriteTransfer(v11, WAVEIN_OPEN_EXIT, v16);
                  return v16;
                }
LABEL_26:
                LeaveCriticalSection(&NumDevsCritSec);
LABEL_27:
                v16 = 2;
                goto LABEL_28;
              }
              v6 -= v13;
            }
            i = *(struct HWAVEOUT__ **)i;
            if ( i == &waveindrvZ )
              goto LABEL_26;
          }
        }
        if ( (_QWORD)v8 )
        {
          *(_QWORD *)v8 = 0;
          if ( (WinMMEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(
              (__int64)phwi,
              (const EVENT_DESCRIPTOR *)WAVEIN_OPEN_ENTER,
              (__int64)pwfx,
              1u,
              &v31);
          goto LABEL_10;
        }
      }
      return 11;
    }
    return 10;
  }
  return 11;
}

```

## disassembly

```asm
0x1800048e0  push    rbp
0x1800048e2  push    rbx
0x1800048e3  push    rsi
0x1800048e4  push    rdi
0x1800048e5  push    r12
0x1800048e7  push    r13
0x1800048e9  push    r14
0x1800048eb  push    r15
0x1800048ed  lea     rbp, [rsp-0Fh]
0x1800048f2  sub     rsp, 0B8h
0x1800048f9  mov     rax, cs:__security_cookie
0x180004900  xor     rax, rsp
0x180004903  mov     [rbp+47h+var_48], rax
0x180004907  xor     r15d, r15d
0x18000490a  mov     [rbp+47h+phwi], rcx
0x18000490e  mov     dword ptr [rbp+47h+var_B0+4], r15d
0x180004912  xorps   xmm0, xmm0
0x180004915  mov     qword ptr [rbp+47h+var_58], r15
0x180004919  mov     rax, r9
0x18000491c  mov     [rbp+47h+dwCallback], rax
0x180004920  mov     rsi, r8
0x180004923  mov     [rbp+47h+var_90], r15
0x180004927  mov     ebx, edx
0x180004929  mov     rdi, rcx
0x18000492c  movups  [rbp+47h+var_78], xmm0
0x180004930  movups  [rbp+47h+var_78+0Ch], xmm0
0x180004934  movups  [rbp+47h+var_88], xmm0
0x180004938  test    r8, r8
0x18000493b  jz      loc_180004B14
0x180004941  mov     r13d, [rbp+47h+fdwOpen]
0x180004945  test    rax, rax
0x180004948  jnz     loc_180004B58
0x18000494e  cmp     ebx, 0FFFFh
0x180004954  movzx   eax, r13w
0x180004958  mov     r14d, 0FFFFFFFFh
0x18000495e  cmovnz  r14d, ebx
0x180004962  cmp     r14d, 0FFFFFFFFh
0x180004966  jz      loc_180004B02
0x18000496c  test    eax, 0FFFF7E10h
0x180004971  jnz     loc_180004B0D
0x180004977  cmp     word ptr [rsi], 1
0x18000497b  jnz     loc_180004B6F
0x180004981  mov     r12d, r13d
0x180004984  and     r12d, 1
0x180004988  mov     [rbp+47h+var_A8], r12d
0x18000498c  jz      loc_180004B88
0x180004992  mov     [rbp+47h+phwi], r15
0x180004996  call    ClientUpdatePnpInfo
0x18000499b  cmp     cs:wTotalWaveInDevs, r15d
0x1800049a2  jz      loc_180004AD2
0x1800049a8  mov     eax, r13d
0x1800049ab  and     eax, 4
0x1800049ae  mov     dword ptr [rbp+47h+var_B0], eax
0x1800049b1  jnz     loc_180004B1B
0x1800049b7  cmp     r14d, 0FFFFFFFFh
0x1800049bb  jz      loc_180004B1B
0x1800049c1  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800049c8  call    cs:__imp_EnterCriticalSection
0x1800049ce  mov     rbx, qword ptr cs:waveindrvZ.unused
0x1800049d5  lea     rdi, waveindrvZ
0x1800049dc  cmp     rbx, rdi
0x1800049df  jz      loc_180004AC5
0x1800049e5  mov     r15d, r14d
0x1800049e8  test    byte ptr [rbx+70h], 2
0x1800049ec  jnz     loc_180004AB9
0x1800049f2  mov     eax, [rbx+58h]
0x1800049f5  cmp     eax, r15d
0x1800049f8  jbe     loc_180004BBD
0x1800049fe  cmp     rbx, rdi
0x180004a01  jz      loc_180004AC5
0x180004a07  lock inc dword ptr [rbx+5Ch]
0x180004a0b  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180004a12  mov     qword ptr [rbp+47h+var_58], rbx
0x180004a16  mov     dword ptr [rbp+47h+var_B0+4], r15d
0x180004a1a  call    cs:__imp_LeaveCriticalSection
0x180004a20  cmp     r14d, 0FFFFFFFFh
0x180004a24  jz      loc_180004BC5
0x180004a2a  test    r12d, r12d
0x180004a2d  jz      loc_180004CCE
0x180004a33  xor     edi, edi
0x180004a35  mov     qword ptr [rbp+47h+var_58], rdi
0x180004a39  mov     rax, [rbp+47h+dwCallback]
0x180004a3d  lea     r9, [rbp+47h+var_88]
0x180004a41  mov     qword ptr [rbp+47h+var_78], rax
0x180004a45  lea     r8, [rbp+47h+var_90]
0x180004a49  mov     rax, [rbp+47h+dwInstance]
0x180004a4d  mov     edx, 34h ; '4'
0x180004a52  mov     qword ptr [rbp+47h+var_78+8], rax
0x180004a56  mov     ecx, r15d
0x180004a59  mov     qword ptr [rbp+47h+var_88], rdi
0x180004a5d  mov     [rbp+47h+var_68], r14d
0x180004a61  mov     qword ptr [rbp+47h+var_88+8], rsi
0x180004a65  mov     rax, [rbx+68h]
0x180004a69  mov     [rbp+47h+var_64], rax
0x180004a6d  mov     rax, [rbx+50h]
0x180004a71  mov     [rsp+0F0h+var_D0], r13
0x180004a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7b  mov     rsi, qword ptr [rbp+47h+var_58]
0x180004a7f  mov     edi, eax
0x180004a81  test    rsi, rsi
0x180004a84  jnz     loc_180004D46
0x180004a8a  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180004a91  call    cs:__imp_EnterCriticalSection
0x180004a97  mov     eax, 0FFFFFFFFh
0x180004a9c  lock xadd [rbx+5Ch], eax
0x180004aa1  cmp     eax, 1
0x180004aa4  jz      loc_180004D83
0x180004aaa  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180004ab1  call    cs:__imp_LeaveCriticalSection
0x180004ab7  jmp     short loc_180004AD7
0x180004ab9  mov     rbx, [rbx]
0x180004abc  cmp     rbx, rdi
0x180004abf  jnz     loc_1800049E8
0x180004ac5  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180004acc  call    cs:__imp_LeaveCriticalSection
0x180004ad2  mov     edi, 2
0x180004ad7  test    r12d, r12d
0x180004ada  jz      loc_180004CF3
0x180004ae0  mov     eax, edi
0x180004ae2  mov     rcx, [rbp+47h+var_48]
0x180004ae6  xor     rcx, rsp; StackCookie
0x180004ae9  call    __security_check_cookie
0x180004aee  add     rsp, 0B8h
0x180004af5  pop     r15
0x180004af7  pop     r14
0x180004af9  pop     r13
0x180004afb  pop     r12
0x180004afd  pop     rdi
0x180004afe  pop     rsi
0x180004aff  pop     rbx
0x180004b00  pop     rbp
0x180004b01  retn
0x180004b02  test    eax, 0FFFF7E04h
0x180004b07  jz      loc_180004977
0x180004b0d  mov     eax, 0Ah
0x180004b12  jmp     short loc_180004AE2
0x180004b14  mov     eax, 0Bh
0x180004b19  jmp     short loc_180004AE2
0x180004b1b  call    WaveMapperInit
0x180004b20  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180004b27  call    cs:__imp_EnterCriticalSection
0x180004b2d  mov     rbx, qword ptr cs:waveindrvZ.unused
0x180004b34  lea     rdi, waveindrvZ
0x180004b3b  cmp     rbx, rdi
0x180004b3e  jz      short loc_180004AC5
0x180004b40  test    byte ptr [rbx+70h], 2
0x180004b44  jnz     loc_180004A07
0x180004b4a  mov     rbx, [rbx]
0x180004b4d  cmp     rbx, rdi
0x180004b50  jz      loc_180004AC5
0x180004b56  jmp     short loc_180004B40
0x180004b58  mov     edx, r13d
0x180004b5b  mov     rcx, rax
0x180004b5e  shr     edx, 10h
0x180004b61  call    ValidateCallbackType
0x180004b66  test    eax, eax
0x180004b68  jz      short loc_180004B14
0x180004b6a  jmp     loc_18000494E
0x180004b6f  cmp     [rsi+10h], r15w
0x180004b74  jz      loc_180004981
0x180004b7a  lea     rax, [rsi+12h]
0x180004b7e  test    rax, rax
0x180004b81  jz      short loc_180004B14
0x180004b83  jmp     loc_180004981
0x180004b88  test    rdi, rdi
0x180004b8b  jz      short loc_180004B14
0x180004b8d  mov     [rdi], r15
0x180004b90  test    cs:WinMMEnableBits, 1
0x180004b97  jz      loc_180004996
0x180004b9d  lea     rax, [rbp+47h+var_58]
0x180004ba1  mov     r9d, 1
0x180004ba7  lea     rdx, WAVEIN_OPEN_ENTER
0x180004bae  mov     [rsp+0F0h+var_D0], rax
0x180004bb3  call    McGenEventWrite_EventWriteTransfer
0x180004bb8  jmp     loc_180004996
0x180004bbd  sub     r15d, eax
0x180004bc0  jmp     loc_180004AB9
0x180004bc5  cmp     qword ptr [rbx+50h], 0
0x180004bca  jnz     loc_180004A2A
0x180004bd0  mov     rcx, rbx; struct _MMDRV *
0x180004bd3  call    mregDecUsagePtr
0x180004bd8  cmp     dword ptr [rbp+47h+var_B0], 0
0x180004bdc  jz      loc_180004C77
0x180004be2  lea     r9, [rbp+47h+var_B0+4]
0x180004be6  mov     edx, r14d
0x180004be9  lea     r8, [rbp+47h+var_58]
0x180004bed  mov     rcx, rdi
0x180004bf0  call    waveReferenceDriverById
0x180004bf5  mov     dword ptr [rbp+47h+var_B0], eax
0x180004bf8  mov     edi, eax
0x180004bfa  test    eax, eax
0x180004bfc  jnz     loc_180004AD7
0x180004c02  mov     r15, qword ptr [rbp+47h+var_58]
0x180004c06  lea     rax, [rbp+47h+var_B0]
0x180004c0a  mov     r8d, dword ptr [rbp+47h+var_B0+4]
0x180004c0e  mov     r9d, 805h
0x180004c14  mov     [rsp+0F0h+var_C0], rax; __int64
0x180004c19  mov     edx, 1
0x180004c1e  mov     qword ptr [rsp+0F0h+var_C8], 0; unsigned __int64
0x180004c27  mov     rcx, r15; struct _MMDRV *
0x180004c2a  mov     [rsp+0F0h+var_D0], 0; unsigned __int16 *
0x180004c33  call    mregHandleInternalMessages
0x180004c38  mov     edi, dword ptr [rbp+47h+var_B0]
0x180004c3b  test    eax, eax
0x180004c3d  jnz     short loc_180004C6A
0x180004c3f  test    edi, edi
0x180004c41  jnz     short loc_180004C6A
0x180004c43  mov     rax, [rbp+47h+dwInstance]
0x180004c47  and     r13d, 0FFFFFFFBh
0x180004c4b  mov     r9, [rbp+47h+dwCallback]; dwCallback
0x180004c4f  mov     r8, rsi; pwfx
0x180004c52  mov     rcx, [rbp+47h+phwi]; phwi
0x180004c56  mov     edx, r14d; uDeviceID
0x180004c59  mov     [rsp+0F0h+var_C8], r13d; fdwOpen
0x180004c5e  mov     [rsp+0F0h+var_D0], rax; dwInstance
0x180004c63  call    waveInOpen
0x180004c68  mov     edi, eax
0x180004c6a  mov     rcx, r15; struct _MMDRV *
0x180004c6d  call    mregDecUsagePtr
0x180004c72  jmp     loc_180004AD7
0x180004c77  xor     r15d, r15d
0x180004c7a  mov     edi, 4
0x180004c7f  cmp     cs:wTotalWaveInDevs, r15d
0x180004c86  jbe     loc_180004AD7
0x180004c8c  mov     rbx, [rbp+47h+dwCallback]
0x180004c90  mov     r14, [rbp+47h+phwi]
0x180004c94  mov     r12, [rbp+47h+dwInstance]
0x180004c98  mov     [rsp+0F0h+var_C8], r13d; fdwOpen
0x180004c9d  mov     r9, rbx; dwCallback
0x180004ca0  mov     r8, rsi; pwfx
0x180004ca3  mov     [rsp+0F0h+var_D0], r12; dwInstance
0x180004ca8  mov     edx, r15d; uDeviceID
0x180004cab  mov     rcx, r14; phwi
0x180004cae  call    waveInOpen
0x180004cb3  mov     edi, eax
0x180004cb5  test    eax, eax
0x180004cb7  jz      short loc_180004CC5
0x180004cb9  inc     r15d
0x180004cbc  cmp     r15d, cs:wTotalWaveInDevs
0x180004cc3  jb      short loc_180004C98
0x180004cc5  mov     r12d, [rbp+47h+var_A8]
0x180004cc9  jmp     loc_180004AD7
0x180004cce  mov     rdx, [rbx+60h]
0x180004cd2  mov     r8d, 20h ; ' '
0x180004cd8  mov     ecx, 2
0x180004cdd  call    NewHandle
0x180004ce2  mov     qword ptr [rbp+47h+var_58], rax
0x180004ce6  mov     rdi, rax
0x180004ce9  test    rax, rax
0x180004cec  jnz     short loc_180004D14
0x180004cee  mov     edi, 7
0x180004cf3  test    cs:WinMMEnableBits, 1
0x180004cfa  jz      loc_180004AE0
0x180004d00  mov     r8d, edi
0x180004d03  lea     rdx, WAVEIN_OPEN_EXIT
0x180004d0a  call    McTemplateU0q_EventWriteTransfer
0x180004d0f  jmp     loc_180004AE0
0x180004d14  lea     rcx, [rax-28h]; lpCriticalSection
0x180004d18  call    cs:__imp_EnterCriticalSection
0x180004d1e  or      dword ptr [rdi-44h], 2
0x180004d22  lea     rcx, HandleListCritSec; lpCriticalSection
0x180004d29  call    cs:__imp_LeaveCriticalSection
0x180004d2f  mov     [rdi], rbx
0x180004d32  mov     [rdi+8], r15d
0x180004d36  mov     [rdi+18h], r14d
0x180004d3a  mov     dword ptr [rdi+1Ch], 0
0x180004d41  jmp     loc_180004A39
0x180004d46  lea     rcx, [rsi-28h]; lpCriticalSection
0x180004d4a  test    eax, eax
0x180004d4c  jnz     short loc_180004D70
0x180004d4e  and     dword ptr [rsi-44h], 0FFFFFFFDh
0x180004d52  call    cs:__imp_LeaveCriticalSection
0x180004d58  lock inc dword ptr [rbx+5Ch]
0x180004d5c  mov     r14, [rbp+47h+phwi]
0x180004d60  mov     rax, [rbp+47h+var_90]
0x180004d64  mov     [r14], rsi
0x180004d67  mov     [rsi+10h], rax
0x180004d6b  jmp     loc_180004A8A
0x180004d70  call    cs:__imp_LeaveCriticalSection
0x180004d76  mov     rcx, rsi
0x180004d79  call    FreeHandle
0x180004d7e  jmp     loc_180004A8A
0x180004d83  mov     rcx, rbx; struct _MMDRV *
0x180004d86  call    ?mregRemoveDriver@@YAXPEAU_MMDRV@@@Z; mregRemoveDriver(_MMDRV *)
0x180004d8b  jmp     loc_180004AAA
```
