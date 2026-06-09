# CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)

- ea: `0x1800236f4`
- end: `0x180023788`
- name: `?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z`
- size: `148`
- prototype: `HWND __fastcall(CImpWorkerWndProc *__hidden this, HWND, unsigned int, unsigned int, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027bf4`

## callees

- `0x1800228cc`
- `0x1800236f4`

## import_xrefs

- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x180023732`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x180023778`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x180023732`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x180023778`

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
        && (result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, -3, 0),
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
      result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, -3, 0);
      *((_QWORD *)this + 1) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800236f4  push    rbx
0x1800236f6  sub     rsp, 30h
0x1800236fa  mov     rax, [rcx+8]
0x1800236fe  mov     rbx, rcx
0x180023701  test    rax, rax
0x180023704  jnz     short loc_180023782
0x180023706  cmp     [rcx+10h], al
0x180023709  jz      short loc_180023759
0x18002370b  cmp     [rcx+20h], rax
0x18002370f  jz      short loc_180023755
0x180023711  cmp     [rcx+18h], rax
0x180023715  jz      short loc_180023755
0x180023717  mov     [rsp+38h+var_10], rcx
0x18002371c  lea     rdx, [rax-3]
0x180023720  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180023727  mov     [rsp+38h+var_18], rax
0x18002372c  xor     r9d, r9d
0x18002372f  xor     r8d, r8d
0x180023732  call    cs:__imp_SHCreateWorkerWindowW
0x180023738  mov     [rbx+8], rax
0x18002373c  test    rax, rax
0x18002373f  jz      short loc_180023755
0x180023741  cmp     byte ptr [rbx+10h], 0
0x180023745  jz      short loc_180023782
0x180023747  mov     rcx, rbx; this
0x18002374a  call    ?AddWndRef@CImpWorkerWndProc@@AEAAXXZ; CImpWorkerWndProc::AddWndRef(void)
0x18002374f  mov     rax, [rbx+8]
0x180023753  jmp     short loc_180023782
0x180023755  xor     eax, eax
0x180023757  jmp     short loc_180023782
0x180023759  xor     r9d, r9d
0x18002375c  mov     [rsp+38h+var_10], rbx
0x180023761  xor     r8d, r8d
0x180023764  mov     [rsp+38h+var_18], 0
0x18002376d  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180023774  lea     rdx, [r9-3]
0x180023778  call    cs:__imp_SHCreateWorkerWindowW
0x18002377e  mov     [rbx+8], rax
0x180023782  add     rsp, 30h
0x180023786  pop     rbx
0x180023787  retn
```
