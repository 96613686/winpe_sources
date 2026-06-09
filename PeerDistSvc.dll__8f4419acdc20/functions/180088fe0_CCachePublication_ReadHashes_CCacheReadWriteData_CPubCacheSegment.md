# CCachePublication::ReadHashes(CCacheReadWriteData *,CPubCacheSegment *)

- ea: `0x180088fe0`
- end: `0x180089335`
- name: `?ReadHashes@CCachePublication@@QEAAKPEAVCCacheReadWriteData@@PEAVCPubCacheSegment@@@Z`
- size: `853`
- prototype: `unsigned int __fastcall(CCachePublication *__hidden this, struct CCacheReadWriteData *, struct CPubCacheSegment *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180092060`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x1800082d0`
- `0x18001fc30`
- `0x180088fe0`
- `0x18013912c`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008924b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008924b`
- `KERNEL32!ReadFile` at `0x1800891ed`
- `KERNEL32!ReadFile` at `0x1800891ed`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180089241`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180089241`

## pseudocode

```c
__int64 __fastcall CCachePublication::ReadHashes(
        CCachePublication *this,
        struct CCacheReadWriteData *a2,
        struct CPubCacheSegment *a3)
{
  __int64 v6; // rbp
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r14
  int v11; // eax
  unsigned int v12; // ebx
  CHostedCacheMsgEncoding *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rdx
  unsigned __int64 v16; // r8
  int v17; // eax
  void *v18; // rcx
  void *v19; // rdx
  DWORD LastError; // eax
  _BYTE v22[72]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v23; // [rsp+80h] [rbp+8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 60, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids);
  }
  InCritSec::InCritSec((InCritSec *)v22, (CCachePublication *)((char *)this + 24), 1);
  if ( a2 )
  {
    if ( *((_QWORD *)a2 + 8) )
    {
      v6 = *((unsigned int *)a2 + 15);
      if ( (_DWORD)v6 )
      {
        v7 = *((unsigned int *)this + 4);
        if ( (int)v7 < 2 || *((_QWORD *)this + 214) == -1 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v7);
          }
          v12 = 4057;
          goto LABEL_53;
        }
        v8 = *((unsigned int *)this + 438);
        v9 = *((_QWORD *)a2 + 9);
        v10 = *((_QWORD *)a3 + 7);
        LOWORD(v23) = 0;
        v11 = AlgIdToHashLen(v8, &v23);
        if ( v11 < 0 )
        {
          v12 = (unsigned __int16)v11;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v14 = *((unsigned int *)this + 438);
            v15 = 63;
LABEL_44:
            WPP_SF_d(*((_QWORD *)v13 + 12), v15, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v14);
          }
LABEL_45:
          if ( v12 )
            goto LABEL_53;
LABEL_54:
          InCritSec::~InCritSec((InCritSec *)v22);
          return v12;
        }
        if ( v9 % (unsigned __int16)v23 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 64, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids);
          }
          v12 = 87;
          goto LABEL_53;
        }
        v16 = v10 + v9;
        v23 = v10 + v9;
        if ( v10 + v9 < v10 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              65,
              WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
              v10,
              v9);
          }
LABEL_26:
          v12 = 774;
LABEL_53:
          *((_DWORD *)this + 4) = 6;
          goto LABEL_54;
        }
        if ( v16 + v6 < v16 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              66,
              WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
              v10 + v9,
              v6);
          }
          goto LABEL_26;
        }
        v17 = HIDWORD(v23);
        v18 = (void *)*((_QWORD *)this + 214);
        *((_DWORD *)this + 450) = v16;
        *((_DWORD *)this + 451) = v17;
        v19 = (void *)*((_QWORD *)a2 + 8);
        NumberOfBytesRead = 0;
        if ( !ReadFile(v18, v19, v6, &NumberOfBytesRead, (LPOVERLAPPED)((char *)this + 1784)) )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError != 997 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_45;
            }
            v15 = 67;
            goto LABEL_43;
          }
          if ( !GetOverlappedResult(*((HANDLE *)this + 214), (LPOVERLAPPED)((char *)this + 1784), &NumberOfBytesRead, 1) )
          {
            LastError = GetLastError();
            v12 = LastError;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_45;
            }
            v15 = 68;
LABEL_43:
            v14 = LastError;
            goto LABEL_44;
          }
        }
        *((_DWORD *)a2 + 14) = NumberOfBytesRead;
        (*(void (__fastcall **)(struct CCacheReadWriteData *))(*(_QWORD *)a2 + 24LL))(a2);
        v12 = 0;
        goto LABEL_54;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 61, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids);
  }
  InCritSec::~InCritSec((InCritSec *)v22);
  return 87;
}

```

## disassembly

```asm
0x180088fe0  mov     [rsp+arg_10], rbx
0x180088fe5  push    rbp
0x180088fe6  push    rsi
0x180088fe7  push    rdi
0x180088fe8  push    r13
0x180088fea  push    r14
0x180088fec  sub     rsp, 50h
0x180088ff0  mov     r14, r8
0x180088ff3  mov     rdi, rdx
0x180088ff6  mov     rsi, rcx
0x180088ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180089000  lea     r13, WPP_GLOBAL_Control
0x180089007  lea     rbx, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008900e  cmp     rcx, r13
0x180089011  jz      short loc_180089033
0x180089013  test    byte ptr [rcx+6Ch], 4
0x180089017  jz      short loc_180089033
0x180089019  cmp     byte ptr [rcx+69h], 4
0x18008901d  jb      short loc_180089033
0x18008901f  mov     rcx, [rcx+60h]
0x180089023  mov     edx, 3Ch ; '<'
0x180089028  mov     r9, rsi
0x18008902b  mov     r8, rbx
0x18008902e  call    WPP_SF_q
0x180089033  lea     rdx, [rsi+18h]; struct CritSec *
0x180089037  mov     r8b, 1; bool
0x18008903a  lea     rcx, [rsp+78h+var_48]; this
0x18008903f  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180089044  test    rdi, rdi
0x180089047  jz      loc_1800892E9
0x18008904d  cmp     qword ptr [rdi+40h], 0
0x180089052  jz      loc_1800892E9
0x180089058  mov     ebp, [rdi+3Ch]
0x18008905b  test    ebp, ebp
0x18008905d  jz      loc_1800892E9
0x180089063  mov     r9d, [rsi+10h]
0x180089067  cmp     r9d, 2
0x18008906b  jl      loc_1800892A6
0x180089071  cmp     qword ptr [rsi+6B0h], 0FFFFFFFFFFFFFFFFh
0x180089079  jz      loc_1800892A6
0x18008907f  mov     ecx, [rsi+6D8h]
0x180089085  lea     rdx, [rsp+78h+arg_0]
0x18008908d  mov     rbx, [rdi+48h]
0x180089091  xor     eax, eax
0x180089093  mov     r14, [r14+38h]
0x180089097  mov     word ptr [rsp+78h+arg_0], ax
0x18008909f  call    ?AlgIdToHashLen@@YAJW4_TNO_HASH_ALG_ID@@PEAG@Z; AlgIdToHashLen(_TNO_HASH_ALG_ID,ushort *)
0x1800890a4  test    eax, eax
0x1800890a6  jns     short loc_1800890E0
0x1800890a8  movzx   ebx, ax
0x1800890ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800890b2  cmp     rcx, r13
0x1800890b5  jz      loc_180089283
0x1800890bb  test    byte ptr [rcx+6Ch], 4
0x1800890bf  jz      loc_180089283
0x1800890c5  cmp     byte ptr [rcx+69h], 1
0x1800890c9  jb      loc_180089283
0x1800890cf  mov     r9d, [rsi+6D8h]
0x1800890d6  mov     edx, 3Fh ; '?'
0x1800890db  jmp     loc_180089273
0x1800890e0  movzx   ecx, word ptr [rsp+78h+arg_0]
0x1800890e8  xor     edx, edx
0x1800890ea  mov     rax, rbx
0x1800890ed  div     rcx
0x1800890f0  test    rdx, rdx
0x1800890f3  jz      short loc_18008912F
0x1800890f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800890fc  cmp     rcx, r13
0x1800890ff  jz      short loc_180089125
0x180089101  test    byte ptr [rcx+6Ch], 4
0x180089105  jz      short loc_180089125
0x180089107  cmp     byte ptr [rcx+69h], 1
0x18008910b  jb      short loc_180089125
0x18008910d  mov     rcx, [rcx+60h]
0x180089111  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180089118  mov     edx, 40h ; '@'
0x18008911d  mov     r9, rbx
0x180089120  call    WPP_SF_q
0x180089125  mov     ebx, 57h ; 'W'
0x18008912a  jmp     loc_1800892D4
0x18008912f  lea     r8, [r14+rbx]
0x180089133  mov     [rsp+78h+arg_0], r8
0x18008913b  cmp     r8, r14
0x18008913e  jnb     short loc_18008917F
0x180089140  mov     rcx, cs:WPP_GLOBAL_Control
0x180089147  cmp     rcx, r13
0x18008914a  jz      short loc_180089175
0x18008914c  test    byte ptr [rcx+6Ch], 4
0x180089150  jz      short loc_180089175
0x180089152  cmp     byte ptr [rcx+69h], 1
0x180089156  jb      short loc_180089175
0x180089158  mov     edx, 41h ; 'A'
0x18008915d  mov     [rsp+78h+lpOverlapped], rbx
0x180089162  mov     r9, r14
0x180089165  mov     rcx, [rcx+60h]
0x180089169  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180089170  call    WPP_SF_qq
0x180089175  mov     ebx, 306h
0x18008917a  jmp     loc_1800892D4
0x18008917f  lea     rax, [r8+rbp]
0x180089183  cmp     rax, r8
0x180089186  jnb     short loc_1800891AF
0x180089188  mov     rcx, cs:WPP_GLOBAL_Control
0x18008918f  cmp     rcx, r13
0x180089192  jz      short loc_180089175
0x180089194  test    byte ptr [rcx+6Ch], 4
0x180089198  jz      short loc_180089175
0x18008919a  cmp     byte ptr [rcx+69h], 1
0x18008919e  jb      short loc_180089175
0x1800891a0  mov     edx, 42h ; 'B'
0x1800891a5  mov     [rsp+78h+lpOverlapped], rbp
0x1800891aa  mov     r9, r8
0x1800891ad  jmp     short loc_180089165
0x1800891af  mov     eax, dword ptr [rsp+78h+arg_0+4]
0x1800891b6  lea     r14, [rsi+6F8h]
0x1800891bd  mov     rcx, [rsi+6B0h]; hFile
0x1800891c4  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800891cc  mov     [r14+10h], r8d
0x1800891d0  mov     r8d, ebp; nNumberOfBytesToRead
0x1800891d3  mov     [rsi+70Ch], eax
0x1800891d9  mov     rdx, [rdi+40h]; lpBuffer
0x1800891dd  mov     [rsp+78h+NumberOfBytesRead], 0
0x1800891e8  mov     [rsp+78h+lpOverlapped], r14; lpOverlapped
0x1800891ed  call    cs:__imp_ReadFile
0x1800891f3  test    eax, eax
0x1800891f5  jnz     loc_180089289
0x1800891fb  call    cs:__imp_GetLastError
0x180089201  mov     ebx, eax
0x180089203  cmp     eax, 3E5h
0x180089208  jz      short loc_180089229
0x18008920a  mov     rcx, cs:WPP_GLOBAL_Control
0x180089211  cmp     rcx, r13
0x180089214  jz      short loc_180089283
0x180089216  test    byte ptr [rcx+6Ch], 4
0x18008921a  jz      short loc_180089283
0x18008921c  cmp     byte ptr [rcx+69h], 1
0x180089220  jb      short loc_180089283
0x180089222  mov     edx, 43h ; 'C'
0x180089227  jmp     short loc_180089270
0x180089229  mov     rcx, [rsi+6B0h]; hFile
0x180089230  lea     r8, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180089238  mov     r9d, 1; bWait
0x18008923e  mov     rdx, r14; lpOverlapped
0x180089241  call    cs:__imp_GetOverlappedResult
0x180089247  test    eax, eax
0x180089249  jnz     short loc_180089289
0x18008924b  call    cs:__imp_GetLastError
0x180089251  mov     ebx, eax
0x180089253  mov     rcx, cs:WPP_GLOBAL_Control
0x18008925a  cmp     rcx, r13
0x18008925d  jz      short loc_180089283
0x18008925f  test    byte ptr [rcx+6Ch], 4
0x180089263  jz      short loc_180089283
0x180089265  cmp     byte ptr [rcx+69h], 1
0x180089269  jb      short loc_180089283
0x18008926b  mov     edx, 44h ; 'D'
0x180089270  mov     r9d, eax
0x180089273  mov     rcx, [rcx+60h]
0x180089277  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008927e  call    WPP_SF_d
0x180089283  test    ebx, ebx
0x180089285  jz      short loc_1800892DB
0x180089287  jmp     short loc_1800892D4
0x180089289  mov     eax, [rsp+78h+NumberOfBytesRead]
0x180089290  mov     rcx, rdi
0x180089293  mov     [rdi+38h], eax
0x180089296  mov     rax, [rdi]
0x180089299  mov     rax, [rax+18h]
0x18008929d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892a2  xor     ebx, ebx
0x1800892a4  jmp     short loc_1800892DB
0x1800892a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800892ad  cmp     rcx, r13
0x1800892b0  jz      short loc_1800892CF
0x1800892b2  test    byte ptr [rcx+6Ch], 4
0x1800892b6  jz      short loc_1800892CF
0x1800892b8  cmp     byte ptr [rcx+69h], 1
0x1800892bc  jb      short loc_1800892CF
0x1800892be  mov     rcx, [rcx+60h]
0x1800892c2  mov     edx, 3Eh ; '>'
0x1800892c7  mov     r8, rbx
0x1800892ca  call    WPP_SF_d
0x1800892cf  mov     ebx, 0FD9h
0x1800892d4  mov     dword ptr [rsi+10h], 6
0x1800892db  lea     rcx, [rsp+78h+var_48]; this
0x1800892e0  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800892e5  mov     eax, ebx
0x1800892e7  jmp     short loc_180089321
0x1800892e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800892f0  cmp     rcx, r13
0x1800892f3  jz      short loc_180089312
0x1800892f5  test    byte ptr [rcx+6Ch], 4
0x1800892f9  jz      short loc_180089312
0x1800892fb  cmp     byte ptr [rcx+69h], 1
0x1800892ff  jb      short loc_180089312
0x180089301  mov     rcx, [rcx+60h]
0x180089305  mov     edx, 3Dh ; '='
0x18008930a  mov     r8, rbx
0x18008930d  call    WPP_SF_
0x180089312  lea     rcx, [rsp+78h+var_48]; this
0x180089317  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18008931c  mov     eax, 57h ; 'W'
0x180089321  mov     rbx, [rsp+78h+arg_10]
0x180089329  add     rsp, 50h
0x18008932d  pop     r14
0x18008932f  pop     r13
0x180089331  pop     rdi
0x180089332  pop     rsi
0x180089333  pop     rbp
0x180089334  retn
```
