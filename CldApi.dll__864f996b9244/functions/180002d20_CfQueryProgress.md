# CfQueryProgress

- ea: `0x180002d20`
- end: `0x180003198`
- name: `CfQueryProgress`
- size: `1144`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x180002d20`
- `0x180011338`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002e5f`
- `ntdll!RtlNtStatusToDosError` at `0x180002eec`
- `ntdll!RtlNtStatusToDosError` at `0x180002f71`
- `ntdll!RtlNtStatusToDosError` at `0x180002ff8`
- `ntdll!RtlNtStatusToDosError` at `0x180003082`
- `ntdll!RtlNtStatusToDosError` at `0x180002e5f`
- `ntdll!RtlNtStatusToDosError` at `0x180002eec`
- `ntdll!RtlNtStatusToDosError` at `0x180002f71`
- `ntdll!RtlNtStatusToDosError` at `0x180002ff8`
- `ntdll!RtlNtStatusToDosError` at `0x180003082`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180002d80`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180002d80`
- `FLTLIB!FilterSendMessage` at `0x1800030da`
- `FLTLIB!FilterSendMessage` at `0x1800030da`

## string_xrefs

- `0x180002f06`: `SetCldMsgCommand Failed`

## pseudocode

```c
__int64 __fastcall CfQueryProgress(int a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // esi
  unsigned int v7; // eax
  int v8; // ebx
  const wchar_t *v9; // rax
  NTSTATUS v10; // edi
  NTSTATUS v11; // ecx
  __int64 v12; // rcx
  signed int v13; // eax
  NTSTATUS v14; // ecx
  unsigned int v15; // eax
  signed int v16; // eax
  NTSTATUS v17; // ecx
  unsigned int v18; // eax
  signed int v19; // eax
  NTSTATUS v20; // ecx
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  signed int v24; // eax
  __int64 OutBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+70h] [rbp-90h]
  unsigned int v32; // [rsp+74h] [rbp-8Ch]
  int v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  bool v35; // [rsp+88h] [rbp-78h]
  __int64 InBuffer; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+CCh] [rbp-34h]
  _DWORD v39[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v40; // [rsp+D8h] [rbp-28h]
  unsigned int v41; // [rsp+DCh] [rbp-24h]
  int v42; // [rsp+138h] [rbp+38h]
  unsigned int v43; // [rsp+13Ch] [rbp+3Ch]
  int v44; // [rsp+140h] [rbp+40h]
  unsigned int v45; // [rsp+144h] [rbp+44h]
  int v46; // [rsp+148h] [rbp+48h]
  unsigned int v47; // [rsp+14Ch] [rbp+4Ch]

  OutBuffer = 0;
  BytesReturned = 0;
  UnbiasedTime = 0;
  memset_0(&v29, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v6 = *a3;
  v7 = 144 * *a3;
  OutBuffer = v7;
  if ( !v6 || a2 && v7 / v6 == 144 )
    v8 = 0;
  else
    v8 = 87;
  if ( v8 )
    v8 |= 0x80070000;
  if ( v8 > -1 )
  {
    v8 = GlobalPortInit(0);
    if ( v8 > -1 )
    {
      InBuffer = 1886219331;
      v37 = 200;
      v38 = 1507328;
      memset_0(v39, 0, 0xB8u);
      v10 = -1073741811;
      if ( HIWORD(v38) )
      {
        if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xE0 )
        {
          v39[0] = 65543;
          v12 = (v37 + 3) & 0xFFFFFFFC;
          v37 = v12;
          v39[1] = v12;
          *((_BYTE *)&InBuffer + v12) = 1;
          v11 = 0;
          ++v37;
        }
        else
        {
          v11 = -1073741789;
        }
      }
      else
      {
        v11 = -1073741811;
      }
      v13 = RtlNtStatusToDosError(v11);
      v8 = v13;
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
      if ( v8 > -1 )
      {
        if ( HIWORD(v38) > 1u )
        {
          if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xE0 )
          {
            v15 = (v37 + 3) & 0xFFFFFFFC;
            v37 = v15;
            if ( (_WORD)v40 )
              LOWORD(v38) = v38 | 1;
            v40 = 131080;
            v41 = v15;
            *(_WORD *)((char *)&InBuffer + v15) = 16385;
            v14 = 0;
            v37 += 2;
          }
          else
          {
            v14 = -1073741789;
          }
        }
        else
        {
          v14 = -1073741811;
        }
        v16 = RtlNtStatusToDosError(v14);
        v8 = v16;
        if ( v16 > 0 )
          v8 = (unsigned __int16)v16 | 0x80070000;
        if ( v8 > -1 )
        {
          if ( HIWORD(v38) > 0xDu )
          {
            if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xE0 )
            {
              v18 = (v37 + 3) & 0xFFFFFFFC;
              v37 = v18;
              if ( (_WORD)v42 )
                LOWORD(v38) = v38 | 1;
              v43 = v18;
              v42 = 262154;
              *(_DWORD *)((char *)&InBuffer + v18) = a1;
              v17 = 0;
              v37 += 4;
            }
            else
            {
              v17 = -1073741789;
            }
          }
          else
          {
            v17 = -1073741811;
          }
          v19 = RtlNtStatusToDosError(v17);
          v8 = v19;
          if ( v19 > 0 )
            v8 = (unsigned __int16)v19 | 0x80070000;
          if ( v8 > -1 )
          {
            if ( HIWORD(v38) > 0xEu )
            {
              if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE0 )
              {
                v21 = (v37 + 3) & 0xFFFFFFFC;
                v37 = v21;
                if ( (_WORD)v44 )
                  LOWORD(v38) = v38 | 1;
                v45 = v21;
                v44 = 524299;
                *(__int64 *)((char *)&InBuffer + v21) = a2;
                v20 = 0;
                v37 += 8;
              }
              else
              {
                v20 = -1073741789;
              }
            }
            else
            {
              v20 = -1073741811;
            }
            v22 = RtlNtStatusToDosError(v20);
            v8 = v22;
            if ( v22 > 0 )
              v8 = (unsigned __int16)v22 | 0x80070000;
            if ( v8 > -1 )
            {
              if ( HIWORD(v38) > 0xFu )
              {
                if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xE0 )
                {
                  v23 = (v37 + 3) & 0xFFFFFFFC;
                  v37 = v23;
                  if ( (_WORD)v46 )
                    LOWORD(v38) = v38 | 1;
                  v46 = 262154;
                  v10 = 0;
                  v47 = v23;
                  *(_DWORD *)((char *)&InBuffer + v23) = OutBuffer;
                  v37 += 4;
                }
                else
                {
                  v10 = -1073741789;
                }
              }
              v24 = RtlNtStatusToDosError(v10);
              v8 = v24;
              if ( v24 > 0 )
                v8 = (unsigned __int16)v24 | 0x80070000;
              if ( v8 > -1 )
              {
                HIDWORD(InBuffer) = 0;
                LOWORD(v38) = v38 & 0xFFFD;
                v8 = FilterSendMessage(hPort, &InBuffer, 0xE0u, &OutBuffer, 8u, &BytesReturned);
                if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024774 )
                {
                  v9 = 0;
                  v6 = (unsigned int)OutBuffer / 0x90;
                  *a3 = (unsigned int)OutBuffer / 0x90;
                }
                else
                {
                  v9 = L"FilterSendMessage returned error";
                }
              }
              else
              {
                v9 = L"SetCldDsMsgQueryProgressBufferLength Failed";
              }
            }
            else
            {
              v9 = L"SetCldDsMsgQueryProgressBuffer Failed";
            }
          }
          else
          {
            v9 = L"SetCldDsMsgQueryProgressFlags Failed";
          }
        }
        else
        {
          v9 = L"SetCldMsgCommand Failed";
        }
      }
      else
      {
        v9 = L"SetVersion Failed";
      }
    }
    else
    {
      v9 = L"GlobalPortInit Failed";
    }
  }
  else
  {
    v9 = L"Invalid Parameter";
  }
  v30 = v9;
  v34 = OutBuffer;
  v35 = a2 != 0;
  v32 = v6;
  v31 = a1;
  v33 = 144;
  TlmLogApiReliability(0x20u, 0, 0, 0, 0, UnbiasedTime, &v29, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002d20  mov     [rsp-8+arg_18], rbx
0x180002d25  push    rbp
0x180002d26  push    rsi
0x180002d27  push    rdi
0x180002d28  push    r12
0x180002d2a  push    r13
0x180002d2c  push    r14
0x180002d2e  push    r15
0x180002d30  lea     rbp, [rsp-0B0h]
0x180002d38  sub     rsp, 1B0h
0x180002d3f  mov     rax, cs:__security_cookie
0x180002d46  xor     rax, rsp
0x180002d49  mov     [rbp+0E0h+var_40], rax
0x180002d50  xor     r13d, r13d
0x180002d53  mov     r15, r8
0x180002d56  mov     r14, rdx
0x180002d59  mov     [rsp+1E0h+OutBuffer], r13
0x180002d5e  mov     r12d, ecx
0x180002d61  mov     [rsp+1E0h+BytesReturned], r13d
0x180002d66  xor     edx, edx; Val
0x180002d68  mov     [rsp+1E0h+UnbiasedTime], r13
0x180002d6d  lea     r8d, [r13+58h]; Size
0x180002d71  lea     rcx, [rsp+1E0h+var_180]; void *
0x180002d76  call    memset_0
0x180002d7b  lea     rcx, [rsp+1E0h+UnbiasedTime]; UnbiasedTime
0x180002d80  call    cs:__imp_QueryUnbiasedInterruptTime
0x180002d86  mov     esi, [r15]
0x180002d89  lea     eax, [rsi+rsi*8]
0x180002d8c  shl     eax, 4
0x180002d8f  mov     [rsp+1E0h+OutBuffer], rax
0x180002d94  test    esi, esi
0x180002d96  jz      short loc_180002DAF
0x180002d98  test    r14, r14
0x180002d9b  jz      short loc_180002DA8
0x180002d9d  xor     edx, edx
0x180002d9f  div     esi
0x180002da1  cmp     eax, 90h
0x180002da6  jz      short loc_180002DAF
0x180002da8  mov     ebx, 57h ; 'W'
0x180002dad  jmp     short loc_180002DB2
0x180002daf  mov     ebx, r13d
0x180002db2  mov     eax, ebx
0x180002db4  or      eax, 80070000h
0x180002db9  test    ebx, ebx
0x180002dbb  cmovnz  ebx, eax
0x180002dbe  cmp     ebx, 0FFFFFFFFh
0x180002dc1  jg      short loc_180002DCF
0x180002dc3  lea     rax, aInvalidParamet; "Invalid Parameter"
0x180002dca  jmp     loc_180003112
0x180002dcf  xor     ecx, ecx
0x180002dd1  call    GlobalPortInit
0x180002dd6  mov     ebx, eax
0x180002dd8  cmp     eax, 0FFFFFFFFh
0x180002ddb  jg      short loc_180002DE9
0x180002ddd  lea     rax, aGlobalportinit; "GlobalPortInit Failed"
0x180002de4  jmp     loc_180003112
0x180002de9  xor     edx, edx; Val
0x180002deb  mov     [rbp+0E0h+InBuffer], 706D6C43h
0x180002df3  mov     r8d, 0B8h; Size
0x180002df9  mov     [rbp+0E0h+var_118], 0C8h
0x180002e00  lea     rcx, [rbp+0E0h+var_110]; void *
0x180002e04  mov     [rbp+0E0h+var_114], 170000h
0x180002e0b  call    memset_0
0x180002e10  mov     edx, 1
0x180002e15  mov     edi, 0C000000Dh
0x180002e1a  cmp     r13w, word ptr [rbp+0E0h+var_114+2]
0x180002e1f  jb      short loc_180002E25
0x180002e21  mov     ecx, edi
0x180002e23  jmp     short loc_180002E5F
0x180002e25  mov     ecx, [rbp+0E0h+var_118]
0x180002e28  lea     rax, [rcx+3]
0x180002e2c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002e30  add     rax, rdx
0x180002e33  cmp     rax, 0E0h
0x180002e39  jbe     short loc_180002E42
0x180002e3b  mov     ecx, 0C0000023h
0x180002e40  jmp     short loc_180002E5F
0x180002e42  add     ecx, 3
0x180002e45  mov     [rbp+0E0h+var_110], 10007h
0x180002e4c  and     ecx, 0FFFFFFFCh
0x180002e4f  mov     [rbp+0E0h+var_118], ecx
0x180002e52  mov     [rbp+0E0h+var_10C], ecx
0x180002e55  mov     byte ptr [rbp+rcx+0E0h+InBuffer], dl
0x180002e59  mov     ecx, r13d; Status
0x180002e5c  add     [rbp+0E0h+var_118], edx
0x180002e5f  call    cs:__imp_RtlNtStatusToDosError
0x180002e65  mov     ebx, eax
0x180002e67  test    eax, eax
0x180002e69  jle     short loc_180002E74
0x180002e6b  movzx   ebx, ax
0x180002e6e  or      ebx, 80070000h
0x180002e74  cmp     ebx, 0FFFFFFFFh
0x180002e77  jg      short loc_180002E85
0x180002e79  lea     rax, aSetversionFail_0; "SetVersion Failed"
0x180002e80  jmp     loc_180003112
0x180002e85  mov     r8d, 1
0x180002e8b  cmp     r8w, word ptr [rbp+0E0h+var_114+2]
0x180002e90  jb      short loc_180002E96
0x180002e92  mov     ecx, edi
0x180002e94  jmp     short loc_180002EEC
0x180002e96  mov     ecx, [rbp+0E0h+var_118]
0x180002e99  mov     edx, 2
0x180002e9e  lea     rax, [rcx+3]
0x180002ea2  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002ea6  add     rax, rdx
0x180002ea9  cmp     rax, 0E0h
0x180002eaf  jbe     short loc_180002EB8
0x180002eb1  mov     ecx, 0C0000023h
0x180002eb6  jmp     short loc_180002EEC
0x180002eb8  lea     eax, [rcx+3]
0x180002ebb  and     eax, 0FFFFFFFCh
0x180002ebe  mov     ecx, eax
0x180002ec0  mov     [rbp+0E0h+var_118], eax
0x180002ec3  cmp     word ptr [rbp+0E0h+var_108], r13w
0x180002ec8  jz      short loc_180002ECF
0x180002eca  or      word ptr [rbp+0E0h+var_114], r8w
0x180002ecf  mov     rax, rcx
0x180002ed2  mov     [rbp+0E0h+var_108], 20008h
0x180002ed9  mov     ecx, 4001h
0x180002ede  mov     [rbp+0E0h+var_104], eax
0x180002ee1  mov     word ptr [rbp+rax+0E0h+InBuffer], cx
0x180002ee6  mov     ecx, r13d; Status
0x180002ee9  add     [rbp+0E0h+var_118], edx
0x180002eec  call    cs:__imp_RtlNtStatusToDosError
0x180002ef2  mov     ebx, eax
0x180002ef4  test    eax, eax
0x180002ef6  jle     short loc_180002F01
0x180002ef8  movzx   ebx, ax
0x180002efb  or      ebx, 80070000h
0x180002f01  cmp     ebx, 0FFFFFFFFh
0x180002f04  jg      short loc_180002F12
0x180002f06  lea     rax, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x180002f0d  jmp     loc_180003112
0x180002f12  mov     eax, 0Dh
0x180002f17  lea     edx, [rax-9]
0x180002f1a  cmp     ax, word ptr [rbp+0E0h+var_114+2]
0x180002f1e  jb      short loc_180002F24
0x180002f20  mov     ecx, edi
0x180002f22  jmp     short loc_180002F71
0x180002f24  mov     ecx, [rbp+0E0h+var_118]
0x180002f27  lea     rax, [rcx+3]
0x180002f2b  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002f2f  add     rax, rdx
0x180002f32  cmp     rax, 0E0h
0x180002f38  jbe     short loc_180002F41
0x180002f3a  mov     ecx, 0C0000023h
0x180002f3f  jmp     short loc_180002F71
0x180002f41  lea     eax, [rcx+3]
0x180002f44  and     eax, 0FFFFFFFCh
0x180002f47  mov     ecx, eax
0x180002f49  mov     [rbp+0E0h+var_118], eax
0x180002f4c  cmp     word ptr [rbp+0E0h+var_A8], r13w
0x180002f51  jz      short loc_180002F5C
0x180002f53  mov     eax, 1
0x180002f58  or      word ptr [rbp+0E0h+var_114], ax
0x180002f5c  mov     [rbp+0E0h+var_A4], ecx
0x180002f5f  mov     [rbp+0E0h+var_A8], 4000Ah
0x180002f66  mov     dword ptr [rbp+rcx+0E0h+InBuffer], r12d
0x180002f6b  mov     ecx, r13d; Status
0x180002f6e  add     [rbp+0E0h+var_118], edx
0x180002f71  call    cs:__imp_RtlNtStatusToDosError
0x180002f77  mov     ebx, eax
0x180002f79  test    eax, eax
0x180002f7b  jle     short loc_180002F86
0x180002f7d  movzx   ebx, ax
0x180002f80  or      ebx, 80070000h
0x180002f86  cmp     ebx, 0FFFFFFFFh
0x180002f89  jg      short loc_180002F97
0x180002f8b  lea     rax, aSetclddsmsgque_0; "SetCldDsMsgQueryProgressFlags Failed"
0x180002f92  jmp     loc_180003112
0x180002f97  mov     eax, 0Eh
0x180002f9c  cmp     ax, word ptr [rbp+0E0h+var_114+2]
0x180002fa0  jb      short loc_180002FA6
0x180002fa2  mov     ecx, edi
0x180002fa4  jmp     short loc_180002FF8
0x180002fa6  mov     ecx, [rbp+0E0h+var_118]
0x180002fa9  mov     edx, 8
0x180002fae  lea     rax, [rcx+3]
0x180002fb2  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002fb6  add     rax, rdx
0x180002fb9  cmp     rax, 0E0h
0x180002fbf  jbe     short loc_180002FC8
0x180002fc1  mov     ecx, 0C0000023h
0x180002fc6  jmp     short loc_180002FF8
0x180002fc8  lea     eax, [rcx+3]
0x180002fcb  and     eax, 0FFFFFFFCh
0x180002fce  mov     ecx, eax
0x180002fd0  mov     [rbp+0E0h+var_118], eax
0x180002fd3  cmp     word ptr [rbp+0E0h+var_A0], r13w
0x180002fd8  jz      short loc_180002FE3
0x180002fda  mov     eax, 1
0x180002fdf  or      word ptr [rbp+0E0h+var_114], ax
0x180002fe3  mov     [rbp+0E0h+var_9C], ecx
0x180002fe6  mov     [rbp+0E0h+var_A0], 8000Bh
0x180002fed  mov     [rbp+rcx+0E0h+InBuffer], r14
0x180002ff2  mov     ecx, r13d; Status
0x180002ff5  add     [rbp+0E0h+var_118], edx
0x180002ff8  call    cs:__imp_RtlNtStatusToDosError
0x180002ffe  mov     ebx, eax
0x180003000  test    eax, eax
0x180003002  jle     short loc_18000300D
0x180003004  movzx   ebx, ax
0x180003007  or      ebx, 80070000h
0x18000300d  cmp     ebx, 0FFFFFFFFh
0x180003010  jg      short loc_18000301E
0x180003012  lea     rax, aSetclddsmsgque_1; "SetCldDsMsgQueryProgressBuffer Failed"
0x180003019  jmp     loc_180003112
0x18000301e  mov     eax, 0Fh
0x180003023  cmp     ax, word ptr [rbp+0E0h+var_114+2]
0x180003027  jnb     short loc_180003080
0x180003029  mov     ecx, [rbp+0E0h+var_118]
0x18000302c  mov     r8d, 4
0x180003032  lea     rax, [rcx+3]
0x180003036  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000303a  add     rax, r8
0x18000303d  cmp     rax, 0E0h
0x180003043  jbe     short loc_18000304C
0x180003045  mov     edi, 0C0000023h
0x18000304a  jmp     short loc_180003080
0x18000304c  mov     edx, dword ptr [rsp+1E0h+OutBuffer]
0x180003050  lea     eax, [rcx+3]
0x180003053  and     eax, 0FFFFFFFCh
0x180003056  mov     ecx, eax
0x180003058  mov     [rbp+0E0h+var_118], eax
0x18000305b  cmp     word ptr [rbp+0E0h+var_98], r13w
0x180003060  jz      short loc_18000306B
0x180003062  mov     eax, 1
0x180003067  or      word ptr [rbp+0E0h+var_114], ax
0x18000306b  mov     [rbp+0E0h+var_98], 4000Ah
0x180003072  mov     edi, r13d
0x180003075  mov     [rbp+0E0h+var_94], ecx
0x180003078  mov     dword ptr [rbp+rcx+0E0h+InBuffer], edx
0x18000307c  add     [rbp+0E0h+var_118], r8d
0x180003080  mov     ecx, edi; Status
0x180003082  call    cs:__imp_RtlNtStatusToDosError
0x180003088  mov     ebx, eax
0x18000308a  test    eax, eax
0x18000308c  jle     short loc_180003097
0x18000308e  movzx   ebx, ax
0x180003091  or      ebx, 80070000h
0x180003097  cmp     ebx, 0FFFFFFFFh
0x18000309a  jg      short loc_1800030A5
0x18000309c  lea     rax, aSetclddsmsgque; "SetCldDsMsgQueryProgressBufferLength Fa"...
0x1800030a3  jmp     short loc_180003112
0x1800030a5  mov     rcx, qword ptr cs:hPort; hPort
0x1800030ac  lea     r9, [rsp+1E0h+OutBuffer]; lpOutBuffer
0x1800030b1  mov     eax, 0FFFDh
0x1800030b6  mov     dword ptr [rbp+0E0h+InBuffer+4], r13d
0x1800030ba  and     word ptr [rbp+0E0h+var_114], ax
0x1800030be  lea     rdx, [rbp+0E0h+InBuffer]; lpInBuffer
0x1800030c2  lea     rax, [rsp+1E0h+BytesReturned]
0x1800030c7  mov     r8d, 0E0h; dwInBufferSize
0x1800030cd  mov     [rsp+1E0h+lpBytesReturned], rax; lpBytesReturned
0x1800030d2  mov     [rsp+1E0h+dwOutBufferSize], 8; dwOutBufferSize
0x1800030da  call    cs:__imp_FilterSendMessage
0x1800030e0  mov     ecx, 80000000h
0x1800030e5  mov     ebx, eax
0x1800030e7  add     eax, ecx
0x1800030e9  test    ecx, eax
0x1800030eb  jnz     short loc_1800030FE
0x1800030ed  cmp     ebx, 8007007Ah
0x1800030f3  jz      short loc_1800030FE
0x1800030f5  lea     rax, aFiltersendmess_1; "FilterSendMessage returned error"
0x1800030fc  jmp     short loc_180003112
0x1800030fe  mov     eax, 38E38E39h
0x180003103  mul     dword ptr [rsp+1E0h+OutBuffer]
0x180003107  mov     rax, r13
0x18000310a  mov     esi, edx
0x18000310c  shr     esi, 5
0x18000310f  mov     [r15], esi
0x180003112  mov     [rsp+1E0h+var_178], rax
0x180003117  test    r14, r14
0x18000311a  mov     eax, dword ptr [rsp+1E0h+OutBuffer]
0x18000311e  mov     ecx, 20h ; ' '
0x180003123  mov     dword ptr [rbp+0E0h+var_160], eax
0x180003126  setnz   [rbp+0E0h+var_158]
0x18000312a  mov     eax, dword ptr [rsp+1E0h+OutBuffer+4]
0x18000312e  xor     r9d, r9d
0x180003131  mov     dword ptr [rbp+0E0h+var_160+4], eax
0x180003134  xor     r8d, r8d
0x180003137  mov     [rsp+1E0h+var_1A8], ebx
0x18000313b  lea     rax, [rsp+1E0h+var_180]
0x180003140  mov     [rsp+1E0h+var_1B0], rax
0x180003145  xor     edx, edx
0x180003147  mov     rax, [rsp+1E0h+UnbiasedTime]
0x18000314c  mov     [rsp+1E0h+lpBytesReturned], rax
0x180003151  mov     qword ptr [rsp+1E0h+dwOutBufferSize], r13
0x180003156  mov     [rsp+1E0h+var_16C], esi
0x18000315a  mov     [rsp+1E0h+var_170], r12d
0x18000315f  mov     [rsp+1E0h+var_168], 90h
0x180003167  call    TlmLogApiReliability
0x18000316c  mov     eax, ebx
0x18000316e  mov     rcx, [rbp+0E0h+var_40]
0x180003175  xor     rcx, rsp; StackCookie
0x180003178  call    __security_check_cookie
0x18000317d  mov     rbx, [rsp+1E0h+arg_18]
0x180003185  add     rsp, 1B0h
0x18000318c  pop     r15
0x18000318e  pop     r14
0x180003190  pop     r13
  ... truncated ...
```
