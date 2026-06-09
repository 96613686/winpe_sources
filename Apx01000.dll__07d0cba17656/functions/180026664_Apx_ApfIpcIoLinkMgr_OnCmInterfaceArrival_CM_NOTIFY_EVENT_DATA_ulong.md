# Apx::ApfIpcIoLinkMgr::OnCmInterfaceArrival(_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x180026664`
- end: `0x180026971`
- name: `?OnCmInterfaceArrival@ApfIpcIoLinkMgr@Apx@@AEAAXPEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `781`
- prototype: `void __fastcall(signed __int64 this, struct _CM_NOTIFY_EVENT_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x180026fb0`

## callees

- `0x18000a12c`
- `0x18000b6e0`
- `0x18000b810`
- `0x18001051c`
- `0x1800205f8`
- `0x180026664`
- `0x1800270ac`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026933`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002686e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002686e`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLinkMgr::OnCmInterfaceArrival(
        signed __int64 this,
        struct _CM_NOTIFY_EVENT_DATA *a2,
        unsigned int a3)
{
  char *v6; // rcx
  __int64 v7; // rdx
  __int64 SymLinkFromCmEventData; // r10
  __int64 v9; // rax
  _WORD *v10; // r8
  _WORD *v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // rcx
  char *FileW; // rax
  unsigned int (__high *v15)(struct HCMNOTIFICATION__ *, void *, enum _CM_NOTIFY_ACTION, struct _CM_NOTIFY_EVENT_DATA *, unsigned int); // rdx
  int v16; // eax
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( *(_QWORD *)(this + 88) )
  {
    v6 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v7 = 34;
LABEL_10:
      WPP_SF_qd(*((_QWORD *)v6 + 2), v7, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids, ~this, 0);
    }
  }
  else
  {
    SymLinkFromCmEventData = Apx::ApfHelper::GetSymLinkFromCmEventData(0, a2, a3);
    if ( SymLinkFromCmEventData )
    {
      v9 = 2147483646;
      v10 = (_WORD *)(this + 118);
      v11 = (_WORD *)SymLinkFromCmEventData;
      v12 = 261;
      do
      {
        if ( !v9 )
          break;
        if ( !*v11 )
          break;
        *v10++ = *v11++;
        --v9;
        --v12;
      }
      while ( v12 );
      v13 = v10 - 1;
      if ( v12 )
        v13 = v10;
      *v13 = 0;
      if ( v12 )
      {
        v6 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, (_DWORD)v10, ~(_DWORD)this, this + 118);
          v6 = (char *)WPP_GLOBAL_Control;
        }
        if ( *(_BYTE *)(this + 117) )
        {
          if ( v6 != (char *)&WPP_GLOBAL_Control && v6[28] < 0 && (unsigned __int8)v6[25] >= 3u )
          {
            v7 = 38;
            goto LABEL_10;
          }
        }
        else
        {
          FileW = (char *)CreateFileW((LPCWSTR)(this + 118), 0xC0000000, 3u, 0, 3u, 0x40800000u, 0);
          *(_QWORD *)(this + 88) = FileW;
          if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            *(_QWORD *)(this + 88) = 0;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                39,
                &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
                ~this,
                LastError);
            }
          }
          else
          {
            if ( *(_BYTE *)(this + 116) )
            {
              v16 = Apx::ApfHelper::RegisterDeviceNotificationW(
                      FileW,
                      v15,
                      (void *)this,
                      (struct HCMNOTIFICATION__ **)(this + 104));
              if ( v16 < 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 28) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_qd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    40,
                    &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
                    ~this,
                    v16);
                }
                *(_QWORD *)(this + 104) = 0;
              }
            }
            LOBYTE(v15) = 1;
            (*(void (__fastcall **)(_QWORD, unsigned int (__high *)(struct HCMNOTIFICATION__ *, void *, enum _CM_NOTIFY_ACTION, struct _CM_NOTIFY_EVENT_DATA *, unsigned int)))(this + 56))(
              *(_QWORD *)(this + 64),
              v15);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && *((char *)WPP_GLOBAL_Control + 28) < 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)&WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
          ~(_DWORD)this,
          SymLinkFromCmEventData,
          v12 == 0 ? 0x7A : 0);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && *((char *)WPP_GLOBAL_Control + 28) < 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
        ~this,
        -2147467262);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180026664  push    rbx
0x180026666  push    rbp
0x180026667  push    rsi
0x180026668  push    rdi
0x180026669  push    r12
0x18002666b  push    r14
0x18002666d  push    r15
0x18002666f  sub     rsp, 40h
0x180026673  mov     edi, r8d
0x180026676  mov     rsi, rdx
0x180026679  mov     rbx, rcx
0x18002667c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026683  lea     r15, WPP_GLOBAL_Control
0x18002668a  lea     r12, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026691  cmp     rcx, r15
0x180026694  jz      short loc_1800266B3
0x180026696  test    byte ptr [rcx+1Ch], 1
0x18002669a  jz      short loc_1800266B3
0x18002669c  cmp     byte ptr [rcx+19h], 5
0x1800266a0  jb      short loc_1800266B3
0x1800266a2  mov     rcx, [rcx+10h]
0x1800266a6  mov     edx, 21h ; '!'
0x1800266ab  mov     r8, r12
0x1800266ae  call    WPP_SF_
0x1800266b3  lea     rbp, [rbx+10h]
0x1800266b7  mov     rcx, rbp; lpCriticalSection
0x1800266ba  call    cs:__imp_EnterCriticalSection
0x1800266c0  xor     r14d, r14d
0x1800266c3  cmp     [rbx+58h], r14
0x1800266c7  jz      short loc_1800266FB
0x1800266c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266d0  cmp     rcx, r15
0x1800266d3  jz      loc_180026930
0x1800266d9  test    byte ptr [rcx+1Ch], 80h
0x1800266dd  jz      loc_180026930
0x1800266e3  cmp     byte ptr [rcx+19h], 3
0x1800266e7  jb      loc_180026930
0x1800266ed  lea     edx, [r14+22h]
0x1800266f1  mov     [rsp+78h+dwCreationDisposition], r14d
0x1800266f6  jmp     loc_18002691E
0x1800266fb  mov     r8d, edi
0x1800266fe  mov     rdx, rsi
0x180026701  xor     ecx, ecx
0x180026703  call    ?GetSymLinkFromCmEventData@ApfHelper@Apx@@SAPEBGW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; Apx::ApfHelper::GetSymLinkFromCmEventData(_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180026708  mov     r10, rax
0x18002670b  test    rax, rax
0x18002670e  jnz     short loc_180026744
0x180026710  mov     rcx, cs:WPP_GLOBAL_Control
0x180026717  cmp     rcx, r15
0x18002671a  jz      loc_180026930
0x180026720  test    byte ptr [rcx+1Ch], 80h
0x180026724  jz      loc_180026930
0x18002672a  cmp     byte ptr [rcx+19h], 2
0x18002672e  jb      loc_180026930
0x180026734  lea     edx, [rax+23h]
0x180026737  mov     [rsp+78h+dwCreationDisposition], 80004002h
0x18002673f  jmp     loc_18002691E
0x180026744  lea     rdi, [rbx+76h]
0x180026748  mov     eax, 7FFFFFFEh
0x18002674d  mov     r8, rdi
0x180026750  mov     rcx, r10
0x180026753  mov     edx, 105h
0x180026758  test    rax, rax
0x18002675b  jz      short loc_18002677C
0x18002675d  movzx   r9d, word ptr [rcx]
0x180026761  test    r9w, r9w
0x180026765  jz      short loc_18002677C
0x180026767  mov     [r8], r9w
0x18002676b  add     rcx, 2
0x18002676f  add     r8, 2
0x180026773  dec     rax
0x180026776  sub     rdx, 1
0x18002677a  jnz     short loc_180026758
0x18002677c  mov     rax, rdx
0x18002677f  lea     rcx, [r8-2]
0x180026783  neg     rax
0x180026786  sbb     r9d, r9d
0x180026789  not     r9d
0x18002678c  and     r9d, 8007007Ah
0x180026793  test    rdx, rdx
0x180026796  cmovnz  rcx, r8
0x18002679a  mov     [rcx], r14w
0x18002679e  jnz     short loc_1800267EA
0x1800267a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267a7  cmp     rcx, r15
0x1800267aa  jz      loc_180026930
0x1800267b0  test    byte ptr [rcx+1Ch], 80h
0x1800267b4  jz      loc_180026930
0x1800267ba  cmp     byte ptr [rcx+19h], 2
0x1800267be  jb      loc_180026930
0x1800267c4  mov     rcx, [rcx+10h]
0x1800267c8  not     rbx
0x1800267cb  mov     [rsp+78h+dwFlagsAndAttributes], r9d
0x1800267d0  mov     edx, 24h ; '$'
0x1800267d5  mov     r9, rbx
0x1800267d8  mov     qword ptr [rsp+78h+dwCreationDisposition], r10
0x1800267dd  mov     r8, r12
0x1800267e0  call    WPP_SF_qSd
0x1800267e5  jmp     loc_180026930
0x1800267ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267f1  cmp     rcx, r15
0x1800267f4  jz      short loc_18002681D
0x1800267f6  test    byte ptr [rcx+1Ch], 80h
0x1800267fa  jz      short loc_18002681D
0x1800267fc  cmp     byte ptr [rcx+19h], 4
0x180026800  jb      short loc_18002681D
0x180026802  mov     rcx, [rcx+10h]
0x180026806  mov     r9, rbx
0x180026809  not     r9
0x18002680c  mov     qword ptr [rsp+78h+dwCreationDisposition], rdi
0x180026811  call    WPP_SF_qS
0x180026816  mov     rcx, cs:WPP_GLOBAL_Control
0x18002681d  cmp     [rbx+75h], r14b
0x180026821  jz      short loc_18002684A
0x180026823  cmp     rcx, r15
0x180026826  jz      loc_180026930
0x18002682c  test    byte ptr [rcx+1Ch], 80h
0x180026830  jz      loc_180026930
0x180026836  cmp     byte ptr [rcx+19h], 3
0x18002683a  jb      loc_180026930
0x180026840  mov     edx, 26h ; '&'
0x180026845  jmp     loc_1800266F1
0x18002684a  xor     r9d, r9d; lpSecurityAttributes
0x18002684d  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x180026852  mov     [rsp+78h+dwFlagsAndAttributes], 40800000h; dwFlagsAndAttributes
0x18002685a  mov     edx, 0C0000000h; dwDesiredAccess
0x18002685f  mov     rcx, rdi; lpFileName
0x180026862  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002686a  lea     r8d, [r9+3]; dwShareMode
0x18002686e  call    cs:__imp_CreateFileW
0x180026874  mov     [rbx+58h], rax
0x180026878  lea     rcx, [rax-1]
0x18002687c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180026880  ja      short loc_1800268E7
0x180026882  cmp     [rbx+74h], r14b
0x180026886  jz      short loc_1800268D2
0x180026888  lea     r9, [rbx+68h]; struct HCMNOTIFICATION__ **
0x18002688c  mov     r8, rbx; void *
0x18002688f  mov     rcx, rax; void *
0x180026892  call    ?RegisterDeviceNotificationW@ApfHelper@Apx@@SAJPEAXP6AKPEAUHCMNOTIFICATION__@@0W4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z0PEAPEAU3@@Z; Apx::ApfHelper::RegisterDeviceNotificationW(void *,ulong (*)(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong),void *,HCMNOTIFICATION__ * *)
0x180026897  test    eax, eax
0x180026899  jns     short loc_1800268D2
0x18002689b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268a2  cmp     rcx, r15
0x1800268a5  jz      short loc_1800268CE
0x1800268a7  test    byte ptr [rcx+1Ch], 80h
0x1800268ab  jz      short loc_1800268CE
0x1800268ad  cmp     byte ptr [rcx+19h], 4
0x1800268b1  jb      short loc_1800268CE
0x1800268b3  mov     rcx, [rcx+10h]
0x1800268b7  mov     r9, rbx
0x1800268ba  not     r9
0x1800268bd  mov     [rsp+78h+dwCreationDisposition], eax
0x1800268c1  mov     edx, 28h ; '('
0x1800268c6  mov     r8, r12
0x1800268c9  call    WPP_SF_qd
0x1800268ce  mov     [rbx+68h], r14
0x1800268d2  mov     rcx, [rbx+40h]
0x1800268d6  mov     r8b, 1
0x1800268d9  mov     rax, [rbx+38h]
0x1800268dd  mov     dl, r8b
0x1800268e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268e5  jmp     short loc_180026930
0x1800268e7  call    cs:__imp_GetLastError
0x1800268ed  test    eax, eax
0x1800268ef  jle     short loc_1800268F9
0x1800268f1  movzx   eax, ax
0x1800268f4  or      eax, 80070000h
0x1800268f9  mov     [rbx+58h], r14
0x1800268fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180026904  cmp     rcx, r15
0x180026907  jz      short loc_180026930
0x180026909  test    byte ptr [rcx+1Ch], 80h
0x18002690d  jz      short loc_180026930
0x18002690f  cmp     byte ptr [rcx+19h], 2
0x180026913  jb      short loc_180026930
0x180026915  mov     edx, 27h ; '''
0x18002691a  mov     [rsp+78h+dwCreationDisposition], eax
0x18002691e  mov     rcx, [rcx+10h]
0x180026922  not     rbx
0x180026925  mov     r9, rbx
0x180026928  mov     r8, r12
0x18002692b  call    WPP_SF_qd
0x180026930  mov     rcx, rbp; lpCriticalSection
0x180026933  call    cs:__imp_LeaveCriticalSection
0x180026939  mov     rcx, cs:WPP_GLOBAL_Control
0x180026940  cmp     rcx, r15
0x180026943  jz      short loc_180026962
0x180026945  test    byte ptr [rcx+1Ch], 1
0x180026949  jz      short loc_180026962
0x18002694b  cmp     byte ptr [rcx+19h], 5
0x18002694f  jb      short loc_180026962
0x180026951  mov     rcx, [rcx+10h]
0x180026955  mov     edx, 29h ; ')'
0x18002695a  mov     r8, r12
0x18002695d  call    WPP_SF_
0x180026962  add     rsp, 40h
0x180026966  pop     r15
0x180026968  pop     r14
0x18002696a  pop     r12
0x18002696c  pop     rdi
0x18002696d  pop     rsi
0x18002696e  pop     rbp
0x18002696f  pop     rbx
0x180026970  retn
```
