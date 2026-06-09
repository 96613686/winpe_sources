# CLoggingMgrImpl::LogScpUpdateFailed(ushort const *,ushort const *,ushort const *,_FILETIME,long)

- ea: `0x18012a790`
- end: `0x18012ab64`
- name: `?LogScpUpdateFailed@CLoggingMgrImpl@@UEAAJPEBG00U_FILETIME@@J@Z`
- size: `980`
- prototype: `__int64 __usercall@<rax>(CLoggingMgrImpl *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct _FILETIME, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x1800083bc`
- `0x180028e84`
- `0x18012637c`
- `0x18012647c`
- `0x180126710`
- `0x18012a790`
- `0x18012b4d0`
- `0x1801448c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18012aa42`
- `ntdll!EtwEventWrite` at `0x18012aa42`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18012a95c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18012a95c`

## pseudocode

```c
__int64 __fastcall CLoggingMgrImpl::LogScpUpdateFailed(
        CLoggingMgrImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        FILETIME FileTime,
        unsigned __int16 a6)
{
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  int v12; // r12d
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  signed int v17; // eax
  const char *v18; // r9
  int v20; // [rsp+30h] [rbp-59h] BYREF
  __int64 v21; // [rsp+38h] [rbp-51h]
  __int64 v22; // [rsp+40h] [rbp-49h] BYREF
  __int64 v23; // [rsp+48h] [rbp-41h]
  __int64 v24; // [rsp+50h] [rbp-39h]
  _QWORD v25[3]; // [rsp+58h] [rbp-31h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 126, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
  }
  v20 = a6;
  v10 = 0;
  SystemTime = 0;
  CErrorMessage::CErrorMessage((CErrorMessage *)&v22, a6);
  InCritSec::InCritSec((InCritSec *)v25, (CLoggingMgrImpl *)((char *)this + 40), 1);
  if ( a2 && a3 && a4 )
  {
    if ( CLoggingMgrImpl::IsObjectStarted(this, 0) )
    {
      v11 = 0;
      if ( CLoggingMgrImpl::PreEventLog(this, 0x23u, 0) )
      {
        v10 = operator new[](0x60u, (const struct std::nothrow_t *)std::nothrow);
        if ( v10 )
        {
          v12 = HIDWORD(v22);
          v21 = v23;
          FileTimeToSystemTime(&FileTime, &SystemTime);
          v13 = -1;
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          *(_QWORD *)v10 = a2;
          v10[2] = 2 * v14 + 2;
          v15 = -1;
          v10[3] = 0;
          do
            ++v15;
          while ( a3[v15] );
          *((_QWORD *)v10 + 2) = a3;
          *((_QWORD *)v10 + 3) = (unsigned int)(2 * v15 + 2);
          do
            ++v13;
          while ( a4[v13] );
          *((_QWORD *)v10 + 4) = a4;
          v10[10] = 2 * v13 + 2;
          v10[11] = 0;
          *((_QWORD *)v10 + 6) = &SystemTime;
          *((_QWORD *)v10 + 7) = 16;
          *((_QWORD *)v10 + 8) = &v20;
          v16 = v21;
          *((_QWORD *)v10 + 9) = 4;
          *((_QWORD *)v10 + 10) = v16;
          *((_QWORD *)v10 + 11) = (unsigned int)(2 * v12 + 2);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 131, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
          }
          v17 = EtwEventWrite(*((_QWORD *)this + 1), ScpUpdateFailedEvent, 6, v10);
          if ( v17 )
          {
            v11 = v17 > 0 ? (unsigned __int16)v17 | 0x80070000 : v17;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 132, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids, v11);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 130, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
          }
          v11 = -2147024882;
        }
      }
      else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 129, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 128, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
      }
      v11 = -2147020842;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        127,
        WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids,
        a2,
        a3,
        a4,
        v20,
        v21,
        v22,
        v23,
        v24,
        v25[0],
        v25[1],
        v25[2]);
    }
    v11 = -2147024809;
  }
  operator delete(v10);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v18 = "success";
    if ( (v11 & 0x80000000) != 0 )
      v18 = "failure";
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      133,
      (unsigned int)WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids,
      (_DWORD)v18,
      v11);
  }
  InCritSec::~InCritSec((InCritSec *)v25);
  CErrorMessage::~CErrorMessage((CErrorMessage *)&v22);
  return v11;
}

```

## disassembly

```asm
0x18012a790  push    rbp
0x18012a792  push    rbx
0x18012a793  push    rsi
0x18012a794  push    rdi
0x18012a795  push    r12
0x18012a797  push    r13
0x18012a799  push    r14
0x18012a79b  push    r15
0x18012a79d  lea     rbp, [rsp-0Fh]
0x18012a7a2  sub     rsp, 98h
0x18012a7a9  mov     rax, cs:__security_cookie
0x18012a7b0  xor     rax, rsp
0x18012a7b3  mov     [rbp+47h+var_50], rax
0x18012a7b7  mov     r15, r9
0x18012a7ba  mov     r14, r8
0x18012a7bd  mov     rsi, rdx
0x18012a7c0  mov     r13, rcx
0x18012a7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a7ca  lea     rax, WPP_GLOBAL_Control
0x18012a7d1  lea     rbx, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012a7d8  cmp     rcx, rax
0x18012a7db  jz      short loc_18012A7FD
0x18012a7dd  test    dword ptr [rcx+6Ch], 80000h
0x18012a7e4  jz      short loc_18012A7FD
0x18012a7e6  cmp     byte ptr [rcx+69h], 4
0x18012a7ea  jb      short loc_18012A7FD
0x18012a7ec  mov     rcx, [rcx+60h]
0x18012a7f0  mov     edx, 7Eh ; '~'
0x18012a7f5  mov     r8, rbx
0x18012a7f8  call    WPP_SF_
0x18012a7fd  movzx   edx, word ptr [rbp+47h+arg_28]; unsigned int
0x18012a801  lea     rcx, [rbp+47h+var_90]; this
0x18012a805  xorps   xmm0, xmm0
0x18012a808  mov     [rbp+47h+var_A0], edx
0x18012a80b  xor     r12d, r12d
0x18012a80e  mov     edi, r12d
0x18012a811  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x18012a815  call    ??0CErrorMessage@@QEAA@K@Z; CErrorMessage::CErrorMessage(ulong)
0x18012a81a  lea     rdx, [r13+28h]; struct CritSec *
0x18012a81e  mov     r8b, 1; bool
0x18012a821  lea     rcx, [rbp+47h+var_78]; this
0x18012a825  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18012a82a  test    rsi, rsi
0x18012a82d  jz      loc_18012AA94
0x18012a833  test    r14, r14
0x18012a836  jz      loc_18012AA94
0x18012a83c  test    r15, r15
0x18012a83f  jz      loc_18012AA94
0x18012a845  xor     edx, edx; bool
0x18012a847  mov     rcx, r13; this
0x18012a84a  call    ?IsObjectStarted@CLoggingMgrImpl@@AEAA_N_N@Z; CLoggingMgrImpl::IsObjectStarted(bool)
0x18012a84f  test    al, al
0x18012a851  jnz     short loc_18012A890
0x18012a853  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a85a  lea     rax, WPP_GLOBAL_Control
0x18012a861  cmp     rcx, rax
0x18012a864  jz      short loc_18012A886
0x18012a866  test    dword ptr [rcx+6Ch], 2000h
0x18012a86d  jz      short loc_18012A886
0x18012a86f  cmp     byte ptr [rcx+69h], 1
0x18012a873  jb      short loc_18012A886
0x18012a875  mov     rcx, [rcx+60h]
0x18012a879  mov     edx, 80h
0x18012a87e  mov     r8, rbx
0x18012a881  call    WPP_SF_
0x18012a886  mov     ebx, 80070FD6h
0x18012a88b  jmp     loc_18012AAD9
0x18012a890  xor     r8d, r8d; bool
0x18012a893  mov     rcx, r13; this
0x18012a896  mov     ebx, r12d
0x18012a899  lea     edx, [r8+23h]; unsigned int
0x18012a89d  call    ?PreEventLog@CLoggingMgrImpl@@AEAA_NK_N@Z; CLoggingMgrImpl::PreEventLog(ulong,bool)
0x18012a8a2  test    al, al
0x18012a8a4  jnz     short loc_18012A8EE
0x18012a8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a8ad  lea     rax, WPP_GLOBAL_Control
0x18012a8b4  cmp     rcx, rax
0x18012a8b7  jz      loc_18012AAD9
0x18012a8bd  test    dword ptr [rcx+6Ch], 2000h
0x18012a8c4  jz      loc_18012AAD9
0x18012a8ca  cmp     byte ptr [rcx+69h], 4
0x18012a8ce  jb      loc_18012AAD9
0x18012a8d4  mov     rcx, [rcx+60h]
0x18012a8d8  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012a8df  mov     edx, 81h
0x18012a8e4  call    WPP_SF_
0x18012a8e9  jmp     loc_18012AAD9
0x18012a8ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012a8f5  mov     ecx, 60h ; '`'; unsigned __int64
0x18012a8fa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18012a8ff  mov     rdi, rax
0x18012a902  test    rax, rax
0x18012a905  jnz     short loc_18012A948
0x18012a907  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a90e  lea     rax, WPP_GLOBAL_Control
0x18012a915  cmp     rcx, rax
0x18012a918  jz      short loc_18012A93E
0x18012a91a  test    dword ptr [rcx+6Ch], 2000h
0x18012a921  jz      short loc_18012A93E
0x18012a923  cmp     byte ptr [rcx+69h], 1
0x18012a927  jb      short loc_18012A93E
0x18012a929  mov     rcx, [rcx+60h]
0x18012a92d  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012a934  mov     edx, 82h
0x18012a939  call    WPP_SF_
0x18012a93e  mov     ebx, 8007000Eh
0x18012a943  jmp     loc_18012AAD9
0x18012a948  mov     rax, [rbp+47h+var_88]
0x18012a94c  lea     rdx, [rbp+47h+SystemTime]; lpSystemTime
0x18012a950  mov     r12d, [rbp+47h+var_8C]
0x18012a954  lea     rcx, [rbp+47h+FileTime]; lpFileTime
0x18012a958  mov     [rbp+47h+var_98], rax
0x18012a95c  call    cs:__imp_FileTimeToSystemTime
0x18012a962  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18012a966  mov     rax, rcx
0x18012a969  xor     edx, edx
0x18012a96b  inc     rax
0x18012a96e  cmp     [rsi+rax*2], dx
0x18012a972  jnz     short loc_18012A96B
0x18012a974  lea     eax, ds:2[rax*2]
0x18012a97b  mov     [rdi], rsi
0x18012a97e  mov     [rdi+8], eax
0x18012a981  mov     rax, rcx
0x18012a984  mov     [rdi+0Ch], edx
0x18012a987  inc     rax
0x18012a98a  cmp     [r14+rax*2], dx
0x18012a98f  jnz     short loc_18012A987
0x18012a991  lea     eax, ds:2[rax*2]
0x18012a998  mov     [rdi+10h], r14
0x18012a99c  mov     [rdi+18h], eax
0x18012a99f  mov     [rdi+1Ch], edx
0x18012a9a2  inc     rcx
0x18012a9a5  cmp     [r15+rcx*2], dx
0x18012a9aa  jnz     short loc_18012A9A2
0x18012a9ac  mov     [rdi+20h], r15
0x18012a9b0  lea     eax, ds:2[rcx*2]
0x18012a9b7  mov     [rdi+28h], eax
0x18012a9ba  lea     rax, [rbp+47h+SystemTime]
0x18012a9be  mov     [rdi+2Ch], edx
0x18012a9c1  mov     [rdi+30h], rax
0x18012a9c5  lea     rax, [rbp+47h+var_A0]
0x18012a9c9  mov     qword ptr [rdi+38h], 10h
0x18012a9d1  mov     [rdi+40h], rax
0x18012a9d5  mov     rax, [rbp+47h+var_98]
0x18012a9d9  mov     qword ptr [rdi+48h], 4
0x18012a9e1  mov     [rdi+50h], rax
0x18012a9e5  lea     eax, ds:2[r12*2]
0x18012a9ed  xor     r12d, r12d
0x18012a9f0  mov     [rdi+58h], eax
0x18012a9f3  mov     [rdi+5Ch], r12d
0x18012a9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a9fe  lea     rsi, WPP_GLOBAL_Control
0x18012aa05  cmp     rcx, rsi
0x18012aa08  jz      short loc_18012AA2E
0x18012aa0a  test    dword ptr [rcx+6Ch], 2000h
0x18012aa11  jz      short loc_18012AA2E
0x18012aa13  cmp     byte ptr [rcx+69h], 4
0x18012aa17  jb      short loc_18012AA2E
0x18012aa19  mov     rcx, [rcx+60h]
0x18012aa1d  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012aa24  mov     edx, 83h
0x18012aa29  call    WPP_SF_
0x18012aa2e  mov     rcx, [r13+8]
0x18012aa32  lea     rdx, ScpUpdateFailedEvent
0x18012aa39  mov     r9, rdi
0x18012aa3c  mov     r8d, 6
0x18012aa42  call    cs:__imp_EtwEventWrite
0x18012aa48  test    eax, eax
0x18012aa4a  jz      loc_18012AAD9
0x18012aa50  jg      short loc_18012AA56
0x18012aa52  mov     ebx, eax
0x18012aa54  jmp     short loc_18012AA5F
0x18012aa56  movzx   ebx, ax
0x18012aa59  or      ebx, 80070000h
0x18012aa5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18012aa66  cmp     rcx, rsi
0x18012aa69  jz      short loc_18012AAD9
0x18012aa6b  test    dword ptr [rcx+6Ch], 2000h
0x18012aa72  jz      short loc_18012AAD9
0x18012aa74  cmp     byte ptr [rcx+69h], 1
0x18012aa78  jb      short loc_18012AAD9
0x18012aa7a  mov     rcx, [rcx+60h]
0x18012aa7e  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012aa85  mov     edx, 84h
0x18012aa8a  mov     r9d, ebx
0x18012aa8d  call    WPP_SF_d
0x18012aa92  jmp     short loc_18012AAD9
0x18012aa94  mov     rcx, cs:WPP_GLOBAL_Control
0x18012aa9b  lea     rax, WPP_GLOBAL_Control
0x18012aaa2  cmp     rcx, rax
0x18012aaa5  jz      short loc_18012AAD4
0x18012aaa7  test    dword ptr [rcx+6Ch], 80000h
0x18012aaae  jz      short loc_18012AAD4
0x18012aab0  cmp     byte ptr [rcx+69h], 1
0x18012aab4  jb      short loc_18012AAD4
0x18012aab6  mov     rcx, [rcx+60h]
0x18012aaba  mov     edx, 7Fh
0x18012aabf  mov     [rsp+0D0h+var_A8], r15
0x18012aac4  mov     r9, rsi
0x18012aac7  mov     r8, rbx
0x18012aaca  mov     [rsp+0D0h+var_B0], r14
0x18012aacf  call    WPP_SF_qqq
0x18012aad4  mov     ebx, 80070057h
0x18012aad9  mov     rcx, rdi; Block
0x18012aadc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012aae1  mov     rcx, cs:WPP_GLOBAL_Control
0x18012aae8  lea     rax, WPP_GLOBAL_Control
0x18012aaef  cmp     rcx, rax
0x18012aaf2  jz      short loc_18012AB30
0x18012aaf4  test    dword ptr [rcx+6Ch], 80000h
0x18012aafb  jz      short loc_18012AB30
0x18012aafd  cmp     byte ptr [rcx+69h], 4
0x18012ab01  jb      short loc_18012AB30
0x18012ab03  mov     rcx, [rcx+60h]
0x18012ab07  lea     rax, aFailure; "failure"
0x18012ab0e  test    ebx, ebx
0x18012ab10  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18012ab14  lea     r9, aSuccess; "success"
0x18012ab1b  mov     edx, 85h
0x18012ab20  cmovs   r9, rax
0x18012ab24  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012ab2b  call    WPP_SF_sd
0x18012ab30  lea     rcx, [rbp+47h+var_78]; this
0x18012ab34  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18012ab39  lea     rcx, [rbp+47h+var_90]; this
0x18012ab3d  call    ??1CErrorMessage@@QEAA@XZ; CErrorMessage::~CErrorMessage(void)
0x18012ab42  mov     eax, ebx
0x18012ab44  mov     rcx, [rbp+47h+var_50]
0x18012ab48  xor     rcx, rsp; StackCookie
0x18012ab4b  call    __security_check_cookie
0x18012ab50  add     rsp, 98h
0x18012ab57  pop     r15
0x18012ab59  pop     r14
0x18012ab5b  pop     r13
0x18012ab5d  pop     r12
0x18012ab5f  pop     rdi
0x18012ab60  pop     rsi
0x18012ab61  pop     rbx
0x18012ab62  pop     rbp
0x18012ab63  retn
```
