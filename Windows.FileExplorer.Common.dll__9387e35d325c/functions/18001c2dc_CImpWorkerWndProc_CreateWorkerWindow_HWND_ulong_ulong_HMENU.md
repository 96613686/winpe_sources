# CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)

- ea: `0x18001c2dc`
- end: `0x18001c36c`
- name: `?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z`
- size: `144`
- prototype: `HWND __fastcall(CImpWorkerWndProc *__hidden this, HWND, unsigned int, unsigned int, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c130`

## callees

- `0x18001c2dc`
- `0x18005d7e0`

## import_xrefs

- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001c318`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001c35c`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001c318`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001c35c`

## pseudocode

```c
HWND __fastcall CImpWorkerWndProc::CreateWorkerWindow(CImpWorkerWndProc *this, HWND a2)
{
  HWND result; // rax

  result = (HWND)*((_QWORD *)this + 1);
  if ( !result )
  {
    if ( *((_BYTE *)this + 16) )
    {
      if ( *((_QWORD *)this + 4)
        && *((_QWORD *)this + 3)
        && (result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, 0, 0, 0),
            (*((_QWORD *)this + 1) = result) != 0) )
      {
        if ( *((_BYTE *)this + 16) )
        {
          CImpWorkerWndProc::AddWndRef(this);
          return (HWND)*((_QWORD *)this + 1);
        }
      }
      else
      {
        return 0;
      }
    }
    else
    {
      result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, 0, 0, 0);
      *((_QWORD *)this + 1) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c2dc  push    rbx
0x18001c2de  sub     rsp, 30h
0x18001c2e2  mov     rax, [rcx+8]
0x18001c2e6  mov     rbx, rcx
0x18001c2e9  test    rax, rax
0x18001c2ec  jnz     short loc_18001C366
0x18001c2ee  cmp     [rcx+10h], al
0x18001c2f1  jz      short loc_18001C33F
0x18001c2f3  cmp     [rcx+20h], rax
0x18001c2f7  jz      short loc_18001C33B
0x18001c2f9  cmp     [rcx+18h], rax
0x18001c2fd  jz      short loc_18001C33B
0x18001c2ff  mov     [rsp+38h+var_10], rcx
0x18001c304  xor     r9d, r9d
0x18001c307  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001c30e  mov     [rsp+38h+var_18], rax
0x18001c313  xor     r8d, r8d
0x18001c316  xor     edx, edx
0x18001c318  call    cs:__imp_SHCreateWorkerWindowW
0x18001c31e  mov     [rbx+8], rax
0x18001c322  test    rax, rax
0x18001c325  jz      short loc_18001C33B
0x18001c327  cmp     byte ptr [rbx+10h], 0
0x18001c32b  jz      short loc_18001C366
0x18001c32d  mov     rcx, rbx; this
0x18001c330  call    ?AddWndRef@CImpWorkerWndProc@@AEAAXXZ; CImpWorkerWndProc::AddWndRef(void)
0x18001c335  mov     rax, [rbx+8]
0x18001c339  jmp     short loc_18001C366
0x18001c33b  xor     eax, eax
0x18001c33d  jmp     short loc_18001C366
0x18001c33f  mov     [rsp+38h+var_10], rbx
0x18001c344  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001c34b  xor     r9d, r9d
0x18001c34e  mov     [rsp+38h+var_18], 0
0x18001c357  xor     r8d, r8d
0x18001c35a  xor     edx, edx
0x18001c35c  call    cs:__imp_SHCreateWorkerWindowW
0x18001c362  mov     [rbx+8], rax
0x18001c366  add     rsp, 30h
0x18001c36a  pop     rbx
0x18001c36b  retn
```
