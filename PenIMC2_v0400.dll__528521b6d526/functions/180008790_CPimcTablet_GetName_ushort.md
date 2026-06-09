# CPimcTablet::GetName(ushort * *)

- ea: `0x180008790`
- end: `0x180008971`
- name: `?GetName@CPimcTablet@@UEAAJPEAPEAG@Z`
- size: `481`
- prototype: `__int64 __fastcall(CPimcTablet *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180008790`
- `0x18000cdb0`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800088af`
- `ole32!CoTaskMemAlloc` at `0x1800088af`
- `ole32!CoTaskMemFree` at `0x18000893a`
- `ole32!CoTaskMemFree` at `0x18000893a`
- `USER32!GetMonitorInfoW` at `0x18000882e`
- `USER32!GetMonitorInfoW` at `0x18000882e`
- `USER32!MonitorFromWindow` at `0x18000880a`
- `USER32!MonitorFromWindow` at `0x18000880a`
- `USER32!GetDesktopWindow` at `0x1800087fc`
- `USER32!GetDesktopWindow` at `0x1800087fc`

## pseudocode

```c
__int64 __fastcall CPimcTablet::GetName(CPimcTablet *this, unsigned __int16 **a2)
{
  signed int v2; // esi
  unsigned int v4; // ebx
  __int64 v5; // rcx
  HWND DesktopWindow; // rax
  HMONITOR v7; // rcx
  BOOL MonitorInfoW; // eax
  _WORD *v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdi
  unsigned __int16 *v14; // rcx
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // r8
  unsigned __int16 *v17; // rdx
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // rax
  tagMONITORINFO mi; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v22[72]; // [rsp+48h] [rbp-70h] BYREF

  v2 = -2147024809;
  v4 = a2 == 0 ? 0x80070057 : 0;
  if ( a2 )
  {
    *a2 = 0;
    v5 = *((_QWORD *)this + 3);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 40LL))(v5);
      return v4;
    }
    mi.cbSize = 104;
    DesktopWindow = GetDesktopWindow();
    v7 = MonitorFromWindow(DesktopWindow, 1u);
    v4 = v7 == 0 ? 0x80000309 : 0;
    if ( v7 )
    {
      MonitorInfoW = GetMonitorInfoW(v7, &mi);
      v4 = !MonitorInfoW ? 0x80000310 : 0;
      if ( MonitorInfoW )
      {
        v9 = v22;
        v10 = 0x7FFFFFFF;
        do
        {
          if ( !*v9 )
            break;
          ++v9;
          --v10;
        }
        while ( v10 );
        v4 = v10 == 0 ? 0x80070057 : 0;
        v11 = (0x7FFFFFFF - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64);
        if ( v10 )
        {
          v12 = v11 + 1;
          if ( v11 + 1 < v11 )
            return (unsigned int)-2147024362;
          v13 = 2 * v12;
          if ( !is_mul_ok(v12, 2u) )
            return (unsigned int)-2147024362;
          v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
          v4 = v14 == 0 ? 0x8007000E : 0;
          if ( v14 )
          {
            v15 = v13 >> 1;
            if ( v15 - 1 > 0x7FFFFFFE )
            {
              v4 = -2147024809;
              if ( v15 )
              {
                *v14 = 0;
                goto LABEL_25;
              }
            }
            else
            {
              v16 = 2147483646 - v15;
              v17 = v14;
              do
              {
                if ( !(v16 + v15) )
                  break;
                v18 = *(unsigned __int16 *)((char *)v17 + v22 - (_BYTE *)v14);
                if ( !v18 )
                  break;
                *v17++ = v18;
                --v15;
              }
              while ( v15 );
              v19 = v17 - 1;
              if ( v15 )
                v19 = v17;
              v2 = v15 == 0 ? 0x8007007A : 0;
              *v19 = 0;
            }
            v4 = v2;
            if ( v2 >= 0 )
            {
              *a2 = v14;
              return v4;
            }
LABEL_25:
            CoTaskMemFree(v14);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180008790  mov     [rsp+arg_10], rbx
0x180008795  mov     [rsp+arg_18], rbp
0x18000879a  push    rsi
0x18000879b  push    rdi
0x18000879c  push    r14
0x18000879e  sub     rsp, 0A0h
0x1800087a5  mov     rax, cs:__security_cookie
0x1800087ac  xor     rax, rsp
0x1800087af  mov     [rsp+0B8h+var_28], rax
0x1800087b7  mov     rax, rdx
0x1800087ba  mov     esi, 80070057h
0x1800087bf  neg     rax
0x1800087c2  mov     r14, rdx
0x1800087c5  sbb     ebx, ebx
0x1800087c7  xor     ebp, ebp
0x1800087c9  not     ebx
0x1800087cb  and     ebx, esi
0x1800087cd  test    rdx, rdx
0x1800087d0  jz      loc_180008947
0x1800087d6  mov     [rdx], rbp
0x1800087d9  mov     rcx, [rcx+18h]
0x1800087dd  test    rcx, rcx
0x1800087e0  jz      short loc_1800087F4
0x1800087e2  mov     rax, [rcx]
0x1800087e5  mov     rax, [rax+28h]
0x1800087e9  call    cs:__guard_dispatch_icall_fptr
0x1800087ef  jmp     loc_180008947
0x1800087f4  mov     [rsp+0B8h+mi.cbSize], 68h ; 'h'
0x1800087fc  call    cs:__imp_GetDesktopWindow
0x180008802  mov     rcx, rax; hwnd
0x180008805  mov     edx, 1; dwFlags
0x18000880a  call    cs:__imp_MonitorFromWindow
0x180008810  mov     rcx, rax; hMonitor
0x180008813  neg     rax
0x180008816  sbb     ebx, ebx
0x180008818  not     ebx
0x18000881a  and     ebx, 80000309h
0x180008820  test    rcx, rcx
0x180008823  jz      loc_180008947
0x180008829  lea     rdx, [rsp+0B8h+mi]; lpmi
0x18000882e  call    cs:__imp_GetMonitorInfoW
0x180008834  mov     ecx, eax
0x180008836  neg     eax
0x180008838  sbb     ebx, ebx
0x18000883a  not     ebx
0x18000883c  and     ebx, 80000310h
0x180008842  test    ecx, ecx
0x180008844  jz      loc_180008947
0x18000884a  mov     r8d, 7FFFFFFFh
0x180008850  lea     rax, [rsp+0B8h+var_70]
0x180008855  mov     ecx, r8d
0x180008858  cmp     [rax], bp
0x18000885b  jz      short loc_180008867
0x18000885d  add     rax, 2
0x180008861  sub     rcx, 1
0x180008865  jnz     short loc_180008858
0x180008867  mov     rax, rcx
0x18000886a  neg     rax
0x18000886d  mov     rax, rcx
0x180008870  sbb     ebx, ebx
0x180008872  sub     r8, rcx
0x180008875  not     ebx
0x180008877  and     ebx, esi
0x180008879  neg     rax
0x18000887c  sbb     rdx, rdx
0x18000887f  and     rdx, r8
0x180008882  test    rcx, rcx
0x180008885  jz      loc_180008947
0x18000888b  lea     rcx, [rdx+1]
0x18000888f  cmp     rcx, rdx
0x180008892  jb      loc_180008942
0x180008898  mov     eax, 2
0x18000889d  mul     rcx
0x1800088a0  mov     rdi, rax
0x1800088a3  test    rdx, rdx
0x1800088a6  jnz     loc_180008942
0x1800088ac  mov     rcx, rax; cb
0x1800088af  call    cs:__imp_CoTaskMemAlloc
0x1800088b5  mov     rcx, rax; pv
0x1800088b8  neg     rax
0x1800088bb  sbb     ebx, ebx
0x1800088bd  not     ebx
0x1800088bf  and     ebx, 8007000Eh
0x1800088c5  test    rcx, rcx
0x1800088c8  jz      short loc_180008947
0x1800088ca  shr     rdi, 1
0x1800088cd  mov     r8d, 7FFFFFFEh
0x1800088d3  lea     rax, [rdi-1]
0x1800088d7  cmp     rax, r8
0x1800088da  ja      short loc_180008930
0x1800088dc  sub     r8, rdi
0x1800088df  lea     r9, [rsp+0B8h+var_70]
0x1800088e4  sub     r9, rcx
0x1800088e7  mov     rdx, rcx
0x1800088ea  lea     rax, [r8+rdi]
0x1800088ee  test    rax, rax
0x1800088f1  jz      short loc_18000890A
0x1800088f3  movzx   eax, word ptr [r9+rdx]
0x1800088f8  test    ax, ax
0x1800088fb  jz      short loc_18000890A
0x1800088fd  mov     [rdx], ax
0x180008900  add     rdx, 2
0x180008904  sub     rdi, 1
0x180008908  jnz     short loc_1800088EA
0x18000890a  test    rdi, rdi
0x18000890d  lea     rax, [rdx-2]
0x180008911  cmovnz  rax, rdx
0x180008915  neg     rdi
0x180008918  sbb     esi, esi
0x18000891a  not     esi
0x18000891c  and     esi, 8007007Ah
0x180008922  mov     [rax], bp
0x180008925  mov     ebx, esi
0x180008927  test    esi, esi
0x180008929  js      short loc_18000893A
0x18000892b  mov     [r14], rcx
0x18000892e  jmp     short loc_180008947
0x180008930  mov     ebx, esi
0x180008932  test    rdi, rdi
0x180008935  jz      short loc_180008925
0x180008937  mov     [rcx], bp
0x18000893a  call    cs:__imp_CoTaskMemFree
0x180008940  jmp     short loc_180008947
0x180008942  mov     ebx, 80070216h
0x180008947  mov     eax, ebx
0x180008949  mov     rcx, [rsp+0B8h+var_28]
0x180008951  xor     rcx, rsp; StackCookie
0x180008954  call    __security_check_cookie
0x180008959  lea     r11, [rsp+0B8h+var_18]
0x180008961  mov     rbx, [r11+30h]
0x180008965  mov     rbp, [r11+38h]
0x180008969  mov     rsp, r11
0x18000896c  pop     r14
0x18000896e  pop     rdi
0x18000896f  pop     rsi
0x180008970  retn
```
