# ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)

- ea: `0x18000b68c`
- end: `0x18000b768`
- name: `?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(ABO_WRAPPER *, ABO_TREE *, const unsigned __int16 *, int, enum ACCESS_GRANTED *)`
- caller_count: `16`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000b3c0`
- `0x18000bf00`
- `0x18000c560`
- `0x18000c990`
- `0x18000cbb0`
- `0x18000ce90`
- `0x18000d040`
- `0x18000d360`
- `0x18000d8f0`
- `0x18000db80`
- `0x18000dea0`
- `0x18000e170`
- `0x18000e3e0`
- `0x18000e6e0`
- `0x18000f110`
- `0x18000f390`

## callees

- `0x180004408`
- `0x180005314`
- `0x1800053bc`
- `0x18000b68c`
- `0x18000b770`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b753`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CheckAccessAndPermissions(
        ABO_WRAPPER *a1,
        ABO_TREE *a2,
        const unsigned __int16 *a3,
        int a4,
        enum ACCESS_GRANTED *a5)
{
  void *CurrentClientToken; // rax
  void *v10; // rbp
  int v11; // ebx
  int v12; // eax

  CurrentClientToken = GetCurrentClientToken(0);
  v10 = CurrentClientToken;
  if ( CurrentClientToken )
  {
    if ( *((_DWORD *)a2 + 16) && a4 == 1 && (unsigned int)(GetTokenImpersonationLevel(CurrentClientToken) - 2) > 1 )
    {
      v11 = -2147023550;
    }
    else
    {
      v12 = ABO_TREE::CheckAccessToAppHostConfig(a2, v10, a4 == 1);
      v11 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -2147024891 && !a4 )
        {
          v11 = ABO_WRAPPER::CheckReadAccessByAppPoolMembership(a1, v10, a3, a5);
          if ( v11 >= 0 && *(_DWORD *)a5 == 3 )
            v11 = -2147024891;
        }
      }
      else if ( a5 )
      {
        if ( a4 == 1 )
        {
          *(_DWORD *)a5 = 0;
        }
        else if ( !a4 )
        {
          *(_DWORD *)a5 = 1;
        }
      }
    }
    CloseHandle(v10);
  }
  else
  {
    return (unsigned int)-2147024891;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000b68c  push    rbx
0x18000b68e  push    rbp
0x18000b68f  push    rsi
0x18000b690  push    rdi
0x18000b691  push    r14
0x18000b693  push    r15
0x18000b695  sub     rsp, 28h
0x18000b699  mov     r15, rcx
0x18000b69c  mov     esi, r9d
0x18000b69f  xor     ecx, ecx; int
0x18000b6a1  mov     r14, r8
0x18000b6a4  mov     rbx, rdx
0x18000b6a7  call    ?GetCurrentClientToken@@YAPEAXH@Z; GetCurrentClientToken(int)
0x18000b6ac  mov     rbp, rax
0x18000b6af  test    rax, rax
0x18000b6b2  jnz     short loc_18000B6BE
0x18000b6b4  mov     ebx, 80070005h
0x18000b6b9  jmp     loc_18000B759
0x18000b6be  cmp     dword ptr [rbx+40h], 0
0x18000b6c2  mov     edi, 1
0x18000b6c7  jz      short loc_18000B6E3
0x18000b6c9  cmp     esi, edi
0x18000b6cb  jnz     short loc_18000B6E3
0x18000b6cd  mov     rcx, rbp; void *
0x18000b6d0  call    ?GetTokenImpersonationLevel@@YA?AW4_SECURITY_IMPERSONATION_LEVEL@@PEAX@Z; GetTokenImpersonationLevel(void *)
0x18000b6d5  add     eax, 0FFFFFFFEh
0x18000b6d8  cmp     eax, edi
0x18000b6da  jbe     short loc_18000B6E3
0x18000b6dc  mov     ebx, 80070542h
0x18000b6e1  jmp     short loc_18000B750
0x18000b6e3  xor     r8d, r8d
0x18000b6e6  mov     rdx, rbp; void *
0x18000b6e9  cmp     esi, edi
0x18000b6eb  mov     rcx, rbx; this
0x18000b6ee  setz    r8b; int
0x18000b6f2  call    ?CheckAccessToAppHostConfig@ABO_TREE@@QEAAJPEAXH@Z; ABO_TREE::CheckAccessToAppHostConfig(void *,int)
0x18000b6f7  mov     ebx, eax
0x18000b6f9  test    eax, eax
0x18000b6fb  js      short loc_18000B71E
0x18000b6fd  mov     rax, [rsp+58h+arg_20]
0x18000b705  test    rax, rax
0x18000b708  jz      short loc_18000B750
0x18000b70a  cmp     esi, edi
0x18000b70c  jnz     short loc_18000B716
0x18000b70e  mov     dword ptr [rax], 0
0x18000b714  jmp     short loc_18000B750
0x18000b716  test    esi, esi
0x18000b718  jnz     short loc_18000B750
0x18000b71a  mov     [rax], edi
0x18000b71c  jmp     short loc_18000B750
0x18000b71e  mov     edi, 80070005h
0x18000b723  cmp     eax, edi
0x18000b725  jnz     short loc_18000B750
0x18000b727  test    esi, esi
0x18000b729  jnz     short loc_18000B750
0x18000b72b  mov     rsi, [rsp+58h+arg_20]
0x18000b733  mov     r8, r14; unsigned __int16 *
0x18000b736  mov     r9, rsi; enum ACCESS_GRANTED *
0x18000b739  mov     rdx, rbp; void *
0x18000b73c  mov     rcx, r15; this
0x18000b73f  call    ?CheckReadAccessByAppPoolMembership@ABO_WRAPPER@@AEAAJPEAXPEBGPEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckReadAccessByAppPoolMembership(void *,ushort const *,ACCESS_GRANTED *)
0x18000b744  mov     ebx, eax
0x18000b746  test    eax, eax
0x18000b748  js      short loc_18000B750
0x18000b74a  cmp     dword ptr [rsi], 3
0x18000b74d  cmovz   ebx, edi
0x18000b750  mov     rcx, rbp; hObject
0x18000b753  call    cs:__imp_CloseHandle
0x18000b759  mov     eax, ebx
0x18000b75b  add     rsp, 28h
0x18000b75f  pop     r15
0x18000b761  pop     r14
0x18000b763  pop     rdi
0x18000b764  pop     rsi
0x18000b765  pop     rbp
0x18000b766  pop     rbx
0x18000b767  retn
```
