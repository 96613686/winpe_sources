# CRdpSessionAgentProxy::SetKey(ushort *)

- ea: `0x140004370`
- end: `0x140004585`
- name: `?SetKey@CRdpSessionAgentProxy@@UEAAJPEAG@Z`
- size: `533`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *this, CHAR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x1400035d8`
- `0x140004370`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x140004454`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140004454`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140004514`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140004514`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::SetKey(CRdpSessionAgentProxy *this, CHAR *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  BSTR v9; // rax
  unsigned int v10; // eax

  v4 = CRdpSessionAgentProxy::AccessCheckWellKnownUser(this, WinLocalSystemSid);
  if ( v4 >= 0 )
  {
    if ( a2 )
    {
      if ( SysStringByteLen((BSTR)a2) == 64 )
      {
        if ( *((_QWORD *)this + 11) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
              CurrentThreadActivityIdPrefix,
              -2147418113);
          }
          return (unsigned int)-2147418113;
        }
        else
        {
          v9 = SysAllocStringByteLen(a2, 0x40u);
          *((_QWORD *)this + 11) = v9;
          if ( !v9 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
                v10,
                -2147024882);
            }
            return (unsigned int)-2147024882;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
            v7,
            -2147024809);
        }
        return (unsigned int)-2147024809;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
          v6,
          -2147467261);
      }
      return (unsigned int)-2147467261;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      v5,
      (__int64)"User not authorized",
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140004370  mov     [rsp+arg_0], rbx
0x140004375  mov     [rsp+arg_8], rsi
0x14000437a  push    rdi
0x14000437b  sub     rsp, 30h
0x14000437f  mov     rdi, rdx
0x140004382  mov     rsi, rcx
0x140004385  mov     edx, 16h; enum WELL_KNOWN_SID_TYPE
0x14000438a  call    ?AccessCheckWellKnownUser@CRdpSessionAgentProxy@@AEAAJW4WELL_KNOWN_SID_TYPE@@@Z; CRdpSessionAgentProxy::AccessCheckWellKnownUser(WELL_KNOWN_SID_TYPE)
0x14000438f  mov     ebx, eax
0x140004391  test    eax, eax
0x140004393  jns     short loc_1400043F9
0x140004395  mov     rax, cs:WPP_GLOBAL_Control
0x14000439c  lea     rcx, WPP_GLOBAL_Control
0x1400043a3  cmp     rax, rcx
0x1400043a6  jz      loc_140004573
0x1400043ac  test    byte ptr [rax+1Ch], 8
0x1400043b0  jz      loc_140004573
0x1400043b6  cmp     byte ptr [rax+19h], 2
0x1400043ba  jb      loc_140004573
0x1400043c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400043c5  lea     rcx, aUserNotAuthori; "User not authorized"
0x1400043cc  mov     [rsp+38h+var_10], ebx
0x1400043d0  mov     [rsp+38h+var_18], rcx
0x1400043d5  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x1400043dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043e3  mov     edx, 19h
0x1400043e8  mov     r9d, eax
0x1400043eb  mov     rcx, [rcx+10h]
0x1400043ef  call    WPP_SF_DsD
0x1400043f4  jmp     loc_140004573
0x1400043f9  test    rdi, rdi
0x1400043fc  jnz     short loc_140004451
0x1400043fe  mov     rax, cs:WPP_GLOBAL_Control
0x140004405  lea     rcx, WPP_GLOBAL_Control
0x14000440c  cmp     rax, rcx
0x14000440f  jz      short loc_140004447
0x140004411  test    byte ptr [rax+1Ch], 8
0x140004415  jz      short loc_140004447
0x140004417  cmp     byte ptr [rax+19h], 2
0x14000441b  jb      short loc_140004447
0x14000441d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004422  mov     rcx, cs:WPP_GLOBAL_Control
0x140004429  lea     edx, [rdi+1Ah]
0x14000442c  mov     r9d, eax
0x14000442f  mov     dword ptr [rsp+38h+var_18], 80004003h
0x140004437  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x14000443e  mov     rcx, [rcx+10h]
0x140004442  call    WPP_SF_Dd
0x140004447  mov     ebx, 80004003h
0x14000444c  jmp     loc_140004573
0x140004451  mov     rcx, rdi; bstr
0x140004454  call    cs:__imp_SysStringByteLen
0x14000445a  mov     edx, 40h ; '@'; len
0x14000445f  cmp     eax, edx
0x140004461  jz      short loc_1400044B8
0x140004463  mov     rax, cs:WPP_GLOBAL_Control
0x14000446a  lea     rcx, WPP_GLOBAL_Control
0x140004471  cmp     rax, rcx
0x140004474  jz      short loc_1400044AE
0x140004476  test    byte ptr [rax+1Ch], 8
0x14000447a  jz      short loc_1400044AE
0x14000447c  cmp     byte ptr [rax+19h], 2
0x140004480  jb      short loc_1400044AE
0x140004482  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004487  mov     rcx, cs:WPP_GLOBAL_Control
0x14000448e  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004495  mov     edx, 1Bh
0x14000449a  mov     dword ptr [rsp+38h+var_18], 80070057h
0x1400044a2  mov     r9d, eax
0x1400044a5  mov     rcx, [rcx+10h]
0x1400044a9  call    WPP_SF_Dd
0x1400044ae  mov     ebx, 80070057h
0x1400044b3  jmp     loc_140004573
0x1400044b8  cmp     qword ptr [rsi+58h], 0
0x1400044bd  jz      short loc_140004511
0x1400044bf  mov     rax, cs:WPP_GLOBAL_Control
0x1400044c6  lea     rcx, WPP_GLOBAL_Control
0x1400044cd  cmp     rax, rcx
0x1400044d0  jz      short loc_14000450A
0x1400044d2  test    byte ptr [rax+1Ch], 8
0x1400044d6  jz      short loc_14000450A
0x1400044d8  cmp     byte ptr [rax+19h], 2
0x1400044dc  jb      short loc_14000450A
0x1400044de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400044e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044ea  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x1400044f1  mov     edx, 1Ch
0x1400044f6  mov     dword ptr [rsp+38h+var_18], 8000FFFFh
0x1400044fe  mov     r9d, eax
0x140004501  mov     rcx, [rcx+10h]
0x140004505  call    WPP_SF_Dd
0x14000450a  mov     ebx, 8000FFFFh
0x14000450f  jmp     short loc_140004573
0x140004511  mov     rcx, rdi; psz
0x140004514  call    cs:__imp_SysAllocStringByteLen
0x14000451a  mov     [rsi+58h], rax
0x14000451e  test    rax, rax
0x140004521  jnz     short loc_140004573
0x140004523  mov     rax, cs:WPP_GLOBAL_Control
0x14000452a  lea     rcx, WPP_GLOBAL_Control
0x140004531  cmp     rax, rcx
0x140004534  jz      short loc_14000456E
0x140004536  test    byte ptr [rax+1Ch], 8
0x14000453a  jz      short loc_14000456E
0x14000453c  cmp     byte ptr [rax+19h], 2
0x140004540  jb      short loc_14000456E
0x140004542  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004547  mov     rcx, cs:WPP_GLOBAL_Control
0x14000454e  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004555  mov     edx, 1Dh
0x14000455a  mov     dword ptr [rsp+38h+var_18], 8007000Eh
0x140004562  mov     r9d, eax
0x140004565  mov     rcx, [rcx+10h]
0x140004569  call    WPP_SF_Dd
0x14000456e  mov     ebx, 8007000Eh
0x140004573  mov     rsi, [rsp+38h+arg_8]
0x140004578  mov     eax, ebx
0x14000457a  mov     rbx, [rsp+38h+arg_0]
0x14000457f  add     rsp, 30h
0x140004583  pop     rdi
0x140004584  retn
```
